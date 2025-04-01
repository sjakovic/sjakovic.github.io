---
layout: post
title: "Building a Robust Invoice Management API with Laravel"
description: "A deep dive into creating a scalable and secure invoice management system using Laravel, featuring PDF generation, advanced filtering, and comprehensive API documentation."
date: 2024-03-29
categories: [Laravel, API, PHP]
---

Managing invoices efficiently is a critical challenge for businesses of all sizes. In this post, I'll share my experience building a comprehensive Invoice Management API using Laravel, exploring the technical decisions, challenges, and solutions that make this system robust and scalable. This example is only a scratch and setup to build something more complex.

## The Problem

Traditional invoice management often involves:
- Manual data entry
- Disconnected systems
- Limited search and filtering capabilities
- No standardized API for integration
- Complex PDF generation processes

Our solution addresses these challenges by providing a modern, RESTful API that automates invoice management while maintaining flexibility and security.

## Key Features

### 1. Authentication & Security
- **Laravel Sanctum Integration**: Secure API authentication with token-based access
- **Role-Based Access Control**: Different permissions for admin, staff, and client users
- **API Rate Limiting**: Protection against abuse and DoS attacks
- **Request Validation**: Comprehensive input validation and sanitization

### 2. Invoice Management
- **CRUD Operations**: Full support for creating, reading, updating, and deleting invoices
- **Status Tracking**: Monitor invoice lifecycle (draft, sent, paid, overdue)
- **Bulk Operations**: Efficient handling of multiple invoices
- **Soft Deletes**: Safe deletion with data recovery capability

### 3. Company Management
- **Multi-Company Support**: Handle multiple companies and their relationships
- **Company Profiles**: Store detailed company information and preferences
- **Address Management**: Multiple address support for billing and shipping
- **Contact Information**: Manage company contacts and their roles

### 4. Invoice Items
- **Flexible Line Items**: Support for various item types and pricing models
- **Tax Calculation**: Automatic tax computation based on rules
- **Discount Handling**: Support for different discount types and calculations
- **Currency Support**: Multi-currency capabilities with conversion

### 5. PDF Generation
- **Professional Templates**: Clean, professional invoice layouts
- **Dynamic Content**: Real-time generation with current data
- **Custom Styling**: Company branding and customization options
- **Multiple Formats**: Support for different paper sizes and orientations

### 6. Advanced Filtering
- **Complex Queries**: Filter by date range, status, amount, and more
- **Search Functionality**: Full-text search across multiple fields
- **Sorting Options**: Multiple sort criteria and directions
- **Pagination**: Efficient handling of large datasets

## Technical Implementation

### Technology Stack
- **Backend Framework**: Laravel 10.x
- **Authentication**: Laravel Sanctum
- **PDF Generation**: DomPDF
- **Database**: MySQL/PostgreSQL
- **API Documentation**: OpenAPI/Swagger

### Database Design
```php
// Example of the Invoice model relationship
class Invoice extends Model
{
    protected $fillable = [
        'company_id',
        'invoice_number',
        'status',
        'due_date',
        'total_amount',
        'currency'
    ];

    public function items()
    {
        return $this->hasMany(InvoiceItem::class);
    }

    public function company()
    {
        return $this->belongsTo(Company::class);
    }
}
```

### API Endpoints
```php
// Example of a controller method with advanced filtering
public function index(Request $request)
{
    $query = Invoice::with(['company', 'items'])
        ->when($request->status, function ($q) use ($request) {
            return $q->where('status', $request->status);
        })
        ->when($request->date_from, function ($q) use ($request) {
            return $q->where('created_at', '>=', $request->date_from);
        })
        ->when($request->search, function ($q) use ($request) {
            return $q->where(function ($query) use ($request) {
                $query->where('invoice_number', 'like', "%{$request->search}%")
                    ->orWhereHas('company', function ($q) use ($request) {
                        $q->where('name', 'like', "%{$request->search}%");
                    });
            });
        });

    return $query->paginate($request->per_page ?? 15);
}
```

## Getting Started

1. Clone the repository:
```bash
git clone https://github.com/sjakovic/invoice-api-laravel.git
```

2. Install dependencies:
```bash
composer install
```

3. Set up environment:
```bash
cp .env.example .env
php artisan key:generate
```

4. Configure database:
```bash
php artisan migrate
php artisan db:seed
```

5. Start the development server:
```bash
php artisan serve
```

## API Documentation

The API is fully documented using OpenAPI/Swagger. You can access the interactive documentation at:
```
http://your-domain/api/documentation
```

### Example API Request
```bash
curl -X POST http://your-domain/api/invoices \
  -H "Authorization: Bearer YOUR_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
    "company_id": 1,
    "invoice_number": "INV-001",
    "due_date": "2024-04-30",
    "items": [
      {
        "description": "Consulting Services",
        "quantity": 10,
        "unit_price": 100
      }
    ]
  }'
```

## Future Enhancements

1. **Real-time Updates**
   - WebSocket integration for live invoice status updates
   - Push notifications for payment reminders

2. **Advanced Analytics**
   - Revenue forecasting
   - Payment trend analysis
   - Customer payment behavior insights

3. **Integration Capabilities**
   - Payment gateway integrations
   - Accounting software sync
   - CRM system integration

4. **Enhanced Security**
   - Two-factor authentication
   - Audit logging
   - IP-based access control

## Contributing

We welcome contributions! Please follow these steps:

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Support

For support, please open an issue in the GitHub repository or contact us at [your-email@example.com](mailto:your-email@example.com). 