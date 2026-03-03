<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cake Shop - Sweet Delights</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: #f9f3e9;
            color: #5d4037;
            line-height: 1.6;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header Styles */
        header {
            background-color: #d4a5a5;
            padding: 1rem 0;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: 700;
            color: #8d6e63;
            text-decoration: none;
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        nav a {
            color: #5d4037;
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s;
        }

        nav a:hover {
            color: #8d6e63;
            text-decoration: underline;
        }

        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            font-size: 1.5rem;
            cursor: pointer;
            color: #5d4037;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, #f9f3e9, #e8d5c5);
            padding: 4rem 0;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .hero h1 {
            font-size: 3rem;
            margin-bottom: 1rem;
            color: #8d6e63;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.1);
        }

        .hero p {
            font-size: 1.2rem;
            max-width: 600px;
            margin: 0 auto 2rem;
            color: #5d4037;
        }

        .btn {
            display: inline-block;
            padding: 12px 30px;
            background-color: #8d6e63;
            color: white;
            border: none;
            border-radius: 30px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
            text-decoration: none;
            margin: 0 10px;
        }

        .btn:hover {
            background-color: #6d4c41;
            transform: translateY(-2px);
            box-shadow: 0 4px 15px rgba(0,0,0,0.2);
        }

        .btn-outline {
            background-color: transparent;
            border: 2px solid #8d6e63;
            color: #8d6e63;
        }

        .btn-outline:hover {
            background-color: #8d6e63;
            color: white;
        }

        /* Features Section */
        .features {
            padding: 4rem 0;
            background-color: white;
        }

        .section-title {
            text-align: center;
            margin-bottom: 3rem;
            font-size: 2.5rem;
            color: #8d6e63;
            position: relative;
        }

        .section-title:after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 60px;
            height: 4px;
            background-color: #8d6e63;
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
        }

        .feature-card {
            background-color: #f9f3e9;
            padding: 2rem;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .feature-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.1);
        }

        .feature-icon {
            font-size: 2.5rem;
            margin-bottom: 1rem;
            color: #8d6e63;
        }

        .feature-card h3 {
            margin-bottom: 1rem;
            color: #5d4037;
        }

        /* Products Section */
        .products {
            padding: 4rem 0;
            background-color: #f9f3e9;
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
        }

        .product-card {
            background-color: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            transition: transform 0.3s;
        }

        .product-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.1);
        }

        .product-image {
            height: 200px;
            background-color: #e8d5c5;
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden;
        }

        .product-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s;
        }

        .product-card:hover .product-image img {
            transform: scale(1.05);
        }

        .product-info {
            padding: 1.5rem;
        }

        .product-info h3 {
            margin-bottom: 0.5rem;
            color: #5d4037;
        }

        .product-price {
            font-size: 1.2rem;
            font-weight: 700;
            color: #8d6e63;
            margin-bottom: 1rem;
        }

        .product-description {
            margin-bottom: 1.5rem;
            color: #7d6660;
        }

        .product-actions {
            display: flex;
            gap: 10px;
        }

        /* About Section */
        .about {
            padding: 4rem 0;
            background-color: white;
        }

        .about-content {
            display: grid;
            grid-template-columns: 1fr;
            gap: 2rem;
        }

        .about-image {
            height: 300px;
            background-color: #e8d5c5;
            border-radius: 10px;
            position: relative;
        }

        .about-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .about-text h2 {
            margin-bottom: 1.5rem;
            color: #8d6e63;
        }

        .about-text p {
            margin-bottom: 1.5rem;
            color: #5d4037;
        }

        /* Testimonials */
        .testimonials {
            padding: 4rem 0;
            background-color: #f9f3e9;
        }

        .testimonials-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .testimonial-card {
            background-color: white;
            padding: 2rem;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            position: relative;
        }

        .testimonial-card:before {
            content: '"';
            position: absolute;
            top: 10px;
            left: 10px;
            font-size: 3rem;
            color: #e8d5c5;
            font-family: Georgia, serif;
            line-height: 1;
        }

        .testimonial-text {
            margin-bottom: 1.5rem;
            color: #5d4037;
            font-style: italic;
        }

        .testimonial-author {
            font-weight: 600;
            color: #8d6e63;
        }

        /* Contact Section */
        .contact {
            padding: 4rem 0;
            background-color: white;
        }

        .contact-container {
            display: grid;
            grid-template-columns: 1fr;
            gap: 2rem;
        }

        .contact-info {
            padding: 2rem;
            background-color: #f9f3e9;
            border-radius: 10px;
        }

        .contact-info h3 {
            margin-bottom: 1.5rem;
            color: #8d6e63;
        }

        .contact-details {
            margin-bottom: 2rem;
        }

        .contact-detail {
            display: flex;
            align-items: center;
            margin-bottom: 1rem;
        }

        .contact-icon {
            width: 40px;
            height: 40px;
            background-color: #8d6e63;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-right: 15px;
            color: white;
            font-size: 1.2rem;
        }

        .contact-form {
            padding: 2rem;
            background-color: #f9f3e9;
            border-radius: 10px;
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 500;
            color: #5d4037;
        }

        .form-control {
            width: 100%;
            padding: 12px 15px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 1rem;
            transition: border-color 0.3s;
        }

        .form-control:focus {
            outline: none;
            border-color: #8d6e63;
        }

        textarea.form-control {
            min-height: 150px;
            resize: vertical;
        }

        /* Footer */
        footer {
            background-color: #8d6e63;
            color: white;
            padding: 2rem 0;
            text-align: center;
        }

        .footer-content {
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .footer-logo {
            font-size: 1.8rem;
            font-weight: 700;
            margin-bottom: 1rem;
        }

        .footer-links {
            display: flex;
            gap: 1.5rem;
            margin-bottom: 1.5rem;
        }

        .footer-links a {
            color: white;
            text-decoration: none;
            transition: color 0.3s;
        }

        .footer-links a:hover {
            color: #e8d5c5;
        }

        .social-icons {
            display: flex;
            gap: 1rem;
            margin-bottom: 1.5rem;
        }

        .social-icon {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background-color: #e8d5c5;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #8d6e63;
            font-size: 1.2rem;
            text-decoration: none;
            transition: background-color 0.3s;
        }

        .social-icon:hover {
            background-color: #8d6e63;
        }

        .copyright {
            font-size: 0.9rem;
            opacity: 0.8;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .header-container {
                flex-direction: column;
                align-items: flex-start;
            }

            nav ul {
                margin-top: 1rem;
                gap: 1rem;
            }

            .hero h1 {
                font-size: 2.2rem;
            }

            .hero p {
                font-size: 1rem;
            }

            .section-title {
                font-size: 2rem;
            }

            .about-content {
                grid-template-columns: 1fr;
            }

            .contact-container {
                grid-template-columns: 1fr;
            }

            .contact-info, .contact-form {
                padding: 1.5rem;
            }
        }

        /* Animation */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .animate {
            animation: fadeIn 0.6s ease forwards;
        }

        /* Special Effects */
        .cake-decoration {
            position: absolute;
            z-index: -1;
            opacity: 0.7;
        }

        .cake-decoration-1 {
            top: 10%;
            left: 10%;
            width: 80px;
            height: 80px;
            background: #d4a5a5;
            border-radius: 50%;
            transform: rotate(30deg);
        }

        .cake-decoration-2 {
            bottom: 15%;
            right: 15%;
            width: 60px;
            height: 60px;
            background: #e8d5c5;
            border-radius: 50%;
            transform: rotate(-45deg);
        }

        .cake-decoration-3 {
            top: 70%;
            left: 30%;
            width: 40px;
            height: 40px;
            background: #8d6e63;
            border-radius: 50%;
            transform: rotate(60deg);
        }

        /* Cart Animation */
        .cart-icon {
            position: relative;
            cursor: pointer;
        }

        .cart-count {
            position: absolute;
            top: -8px;
            right: -8px;
            background-color: #8d6e63;
            color: white;
            border-radius: 50%;
            width: 20px;
            height: 20px;
            display: flex;
            align-items: center;
         
This website for making a cake
