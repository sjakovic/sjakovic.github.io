---
layout: default
title: Privacy Policy
---

<header>
    <div class="container">
        <div class="header-content">
            <h1>Privacy Policy</h1>
            <p>Your privacy is important to us</p>
        </div>
    </div>
</header>

<main>
    <section class="privacy-content">
        <div class="container">
            <div class="content-wrapper">
                <p><strong>Last updated:</strong> {{ 'now' | date: "%B %d, %Y" }}</p>
                
                <h2>1. Introduction</h2>
                <p>Eternia Solutions LLC ("we," "our," or "us") is committed to protecting your privacy. This Privacy Policy explains how we collect, use, disclose, and safeguard your information when you visit our website at eterniasolutions.io or contact us for our services.</p>
                
                <h2>2. Information We Collect</h2>
                <h3>2.1 Personal Information</h3>
                <p>We may collect personal information that you voluntarily provide to us when you:</p>
                <ul>
                    <li>Contact us through our website</li>
                    <li>Request a quote or consultation</li>
                    <li>Subscribe to our newsletter</li>
                    <li>Engage our services</li>
                </ul>
                <p>This information may include:</p>
                <ul>
                    <li>Name and contact information (email, phone number)</li>
                    <li>Company name and position</li>
                    <li>Project requirements and technical specifications</li>
                    <li>Communication preferences</li>
                </ul>
                
                <h3>2.2 Automatically Collected Information</h3>
                <p>When you visit our website, we automatically collect certain information about your device, including:</p>
                <ul>
                    <li>IP address</li>
                    <li>Browser type and version</li>
                    <li>Operating system</li>
                    <li>Pages visited and time spent</li>
                    <li>Referring website</li>
                </ul>
                
                <h2>3. How We Use Your Information</h2>
                <p>We use the information we collect to:</p>
                <ul>
                    <li>Provide and improve our services</li>
                    <li>Respond to your inquiries and requests</li>
                    <li>Send you technical information and updates</li>
                    <li>Analyze website usage and improve user experience</li>
                    <li>Comply with legal obligations</li>
                </ul>
                
                <h2>4. Information Sharing and Disclosure</h2>
                <p>We do not sell, trade, or otherwise transfer your personal information to third parties without your consent, except in the following circumstances:</p>
                <ul>
                    <li>To comply with legal requirements</li>
                    <li>To protect our rights and safety</li>
                    <li>With service providers who assist in our operations (under strict confidentiality agreements)</li>
                </ul>
                
                <h2>5. Data Security</h2>
                <p>We implement appropriate technical and organizational measures to protect your personal information against unauthorized access, alteration, disclosure, or destruction. However, no method of transmission over the internet is 100% secure.</p>
                
                <h2>6. Your Rights (GDPR Compliance)</h2>
                <p>If you are a resident of the European Economic Area (EEA), you have the following rights:</p>
                <ul>
                    <li><strong>Access:</strong> Request access to your personal information</li>
                    <li><strong>Rectification:</strong> Request correction of inaccurate information</li>
                    <li><strong>Erasure:</strong> Request deletion of your personal information</li>
                    <li><strong>Portability:</strong> Request transfer of your data to another service</li>
                    <li><strong>Objection:</strong> Object to processing of your personal information</li>
                    <li><strong>Restriction:</strong> Request restriction of processing</li>
                </ul>
                
                <h2>7. Cookies and Tracking Technologies</h2>
                <p>Our website may use cookies and similar tracking technologies to enhance your experience. You can control cookie settings through your browser preferences.</p>
                
                <h2>8. Third-Party Links</h2>
                <p>Our website may contain links to third-party websites. We are not responsible for the privacy practices of these external sites.</p>
                
                <h2>9. Children's Privacy</h2>
                <p>Our services are not intended for individuals under 18 years of age. We do not knowingly collect personal information from children.</p>
                
                <h2>10. International Data Transfers</h2>
                <p>Your information may be transferred to and processed in countries other than your own. We ensure appropriate safeguards are in place for such transfers.</p>
                
                <h2>11. Changes to This Privacy Policy</h2>
                <p>We may update this Privacy Policy from time to time. We will notify you of any changes by posting the new Privacy Policy on this page and updating the "Last updated" date.</p>
                
                <h2>12. Contact Us</h2>
                <p>If you have any questions about this Privacy Policy or our data practices, please contact us:</p>
                <div class="contact-info">
                    <p><strong>Email:</strong> <a href="mailto:office@eterniasolutions.io">office@eterniasolutions.io</a></p>
                    <p><strong>Address:</strong> Eternia Solutions LLC, Registered Agents Inc, 30 N Gould St Ste R, Sheridan, WY 82801</p>
                </div>
            </div>
        </div>
    </section>
</main>

<style>
    .privacy-content {
        padding: calc(var(--spacing) * 12) 0;
    }
    
    .content-wrapper {
        max-width: 800px;
        margin: 0 auto;
        background: white;
        padding: calc(var(--spacing) * 6);
        border-radius: 15px;
        box-shadow: 0 5px 20px rgba(0, 0, 0, 0.05);
    }
    
    .content-wrapper h2 {
        color: var(--primary-dark);
        margin: calc(var(--spacing) * 4) 0 calc(var(--spacing) * 2);
        font-size: 1.5em;
        font-weight: 700;
    }
    
    .content-wrapper h3 {
        color: var(--primary-dark);
        margin: calc(var(--spacing) * 3) 0 calc(var(--spacing) * 1);
        font-size: 1.2em;
        font-weight: 600;
    }
    
    .content-wrapper p {
        margin-bottom: calc(var(--spacing) * 2);
        line-height: 1.7;
        color: var(--text-light);
    }
    
    .content-wrapper ul {
        margin-bottom: calc(var(--spacing) * 2);
        padding-left: calc(var(--spacing) * 3);
    }
    
    .content-wrapper li {
        margin-bottom: calc(var(--spacing) * 0.5);
        color: var(--text-light);
    }
    
    .contact-info {
        background: var(--background-alt);
        padding: calc(var(--spacing) * 3);
        border-radius: 10px;
        margin-top: calc(var(--spacing) * 2);
    }
    
    .contact-info p {
        margin-bottom: calc(var(--spacing) * 1);
    }
    
    .contact-info a {
        color: var(--primary);
        text-decoration: none;
    }
    
    .contact-info a:hover {
        color: var(--primary-dark);
        text-decoration: underline;
    }
    
    @media (max-width: 768px) {
        .content-wrapper {
            padding: calc(var(--spacing) * 3);
        }
    }
</style> 