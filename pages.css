/* ============================================
   THRIVE PEAK PERFORMANCE - JAVASCRIPT
   ============================================ */

document.addEventListener('DOMContentLoaded', function() {
    
    // Mobile Menu Toggle
    const mobileMenuBtn = document.querySelector('.mobile-menu-btn');
    const navLinks = document.querySelector('.nav-links');
    
    if (mobileMenuBtn) {
        mobileMenuBtn.addEventListener('click', function() {
            this.classList.toggle('active');
            navLinks.classList.toggle('mobile-open');
            document.body.classList.toggle('menu-open');
        });
    }
    
    // Smooth Scroll for Anchor Links
    document.querySelectorAll('a[href^="#"]').forEach(anchor => {
        anchor.addEventListener('click', function(e) {
            const href = this.getAttribute('href');
            if (href !== '#') {
                e.preventDefault();
                const target = document.querySelector(href);
                if (target) {
                    const navHeight = document.querySelector('.main-nav').offsetHeight;
                    const targetPosition = target.getBoundingClientRect().top + window.pageYOffset - navHeight - 20;
                    
                    window.scrollTo({
                        top: targetPosition,
                        behavior: 'smooth'
                    });
                    
                    // Close mobile menu if open
                    if (navLinks.classList.contains('mobile-open')) {
                        mobileMenuBtn.classList.remove('active');
                        navLinks.classList.remove('mobile-open');
                        document.body.classList.remove('menu-open');
                    }
                }
            }
        });
    });
    
    // Navbar Background on Scroll
    const mainNav = document.querySelector('.main-nav');
    let lastScroll = 0;
    
    window.addEventListener('scroll', function() {
        const currentScroll = window.pageYOffset;
        
        if (currentScroll > 100) {
            mainNav.classList.add('scrolled');
        } else {
            mainNav.classList.remove('scrolled');
        }
        
        lastScroll = currentScroll;
    });
    
    // Services Nav Active State on Scroll
    const serviceNavItems = document.querySelectorAll('.service-nav-item');
    const serviceSections = document.querySelectorAll('.service-detail-section');
    
    if (serviceNavItems.length > 0 && serviceSections.length > 0) {
        window.addEventListener('scroll', function() {
            let current = '';
            const navHeight = document.querySelector('.main-nav').offsetHeight + 80;
            
            serviceSections.forEach(section => {
                const sectionTop = section.offsetTop - navHeight - 100;
                const sectionHeight = section.offsetHeight;
                
                if (window.pageYOffset >= sectionTop && window.pageYOffset < sectionTop + sectionHeight) {
                    current = section.getAttribute('id');
                }
            });
            
            serviceNavItems.forEach(item => {
                item.classList.remove('active');
                if (item.getAttribute('href') === '#' + current) {
                    item.classList.add('active');
                }
            });
        });
    }
    
    // Animate Elements on Scroll
    const observerOptions = {
        root: null,
        rootMargin: '0px',
        threshold: 0.1
    };
    
    const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
            if (entry.isIntersecting) {
                entry.target.classList.add('animate-in');
                observer.unobserve(entry.target);
            }
        });
    }, observerOptions);
    
    // Elements to animate
    const animateElements = document.querySelectorAll(
        '.goal-card, .service-card-mini, .trust-feature, .testimonial-card, ' +
        '.process-step, .modality-card, .benefit-category, .team-card, ' +
        '.faq-item, .timeline-item, .value-card'
    );
    
    animateElements.forEach(el => {
        el.classList.add('animate-element');
        observer.observe(el);
    });
    
    // Form Submission Handler
    const contactForm = document.querySelector('.contact-form');
    
    if (contactForm) {
        contactForm.addEventListener('submit', function(e) {
            e.preventDefault();
            
            // Get form data
            const formData = new FormData(this);
            const data = Object.fromEntries(formData);
            
            // Here you would typically send the data to a server
            console.log('Form submitted:', data);
            
            // Show success message (you can customize this)
            const btn = this.querySelector('button[type="submit"]');
            const originalText = btn.textContent;
            btn.textContent = 'Message Sent!';
            btn.disabled = true;
            
            setTimeout(() => {
                btn.textContent = originalText;
                btn.disabled = false;
                this.reset();
            }, 3000);
        });
    }
    
    // Newsletter Form Handler
    const newsletterForm = document.querySelector('.newsletter-form');
    
    if (newsletterForm) {
        newsletterForm.addEventListener('submit', function(e) {
            e.preventDefault();
            
            const email = this.querySelector('input[type="email"]').value;
            console.log('Newsletter signup:', email);
            
            const btn = this.querySelector('button[type="submit"]');
            const originalText = btn.textContent;
            btn.textContent = 'Subscribed!';
            btn.disabled = true;
            
            setTimeout(() => {
                btn.textContent = originalText;
                btn.disabled = false;
                this.reset();
            }, 3000);
        });
    }
    
    // Counter Animation for Stats
    const counters = document.querySelectorAll('.stat-number');
    
    const animateCounter = (counter) => {
        const target = counter.innerText;
        const isPercentage = target.includes('%');
        const hasPlus = target.includes('+');
        const hasX = target.includes('x');
        
        // Extract numeric value
        let numericValue = parseFloat(target.replace(/[^0-9.]/g, ''));
        
        if (isNaN(numericValue)) {
            return; // Skip non-numeric values like "Board"
        }
        
        const duration = 2000;
        const increment = numericValue / (duration / 16);
        let current = 0;
        
        const updateCounter = () => {
            current += increment;
            if (current < numericValue) {
                let displayValue = Math.floor(current);
                if (isPercentage) displayValue += '%';
                if (hasPlus) displayValue += '+';
                if (hasX) displayValue += 'x';
                counter.innerText = displayValue;
                requestAnimationFrame(updateCounter);
            } else {
                counter.innerText = target;
            }
        };
        
        updateCounter();
    };
    
    const statsObserver = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
            if (entry.isIntersecting) {
                animateCounter(entry.target);
                statsObserver.unobserve(entry.target);
            }
        });
    }, { threshold: 0.5 });
    
    counters.forEach(counter => {
        statsObserver.observe(counter);
    });
    
    // Parallax Effect for Hero Background
    const heroSection = document.querySelector('.hero, .hocatt-hero');
    
    if (heroSection) {
        window.addEventListener('scroll', function() {
            const scrolled = window.pageYOffset;
            const heroHeight = heroSection.offsetHeight;
            
            if (scrolled < heroHeight) {
                const pattern = heroSection.querySelector('.hero-pattern, .hocatt-hero-bg');
                if (pattern) {
                    pattern.style.transform = `translateY(${scrolled * 0.3}px)`;
                }
            }
        });
    }
    
    // Add loading class removal
    document.body.classList.add('loaded');
    
});

// Add CSS for animations via JavaScript
const style = document.createElement('style');
style.textContent = `
    .animate-element {
        opacity: 0;
        transform: translateY(30px);
        transition: opacity 0.6s ease, transform 0.6s ease;
    }
    
    .animate-element.animate-in {
        opacity: 1;
        transform: translateY(0);
    }
    
    .nav-links.mobile-open {
        display: flex;
        position: fixed;
        top: 70px;
        left: 0;
        right: 0;
        bottom: 0;
        background: var(--color-dark);
        flex-direction: column;
        align-items: center;
        justify-content: center;
        gap: 2rem;
        z-index: 999;
    }
    
    .mobile-menu-btn.active span:nth-child(1) {
        transform: rotate(45deg) translate(5px, 5px);
    }
    
    .mobile-menu-btn.active span:nth-child(2) {
        opacity: 0;
    }
    
    .mobile-menu-btn.active span:nth-child(3) {
        transform: rotate(-45deg) translate(7px, -6px);
    }
    
    body.menu-open {
        overflow: hidden;
    }
    
    .main-nav.scrolled {
        background: rgba(10, 10, 10, 0.98);
        box-shadow: 0 4px 20px rgba(0, 0, 0, 0.3);
    }
`;
document.head.appendChild(style);
