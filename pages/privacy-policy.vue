<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-12 px-0">
        <NavBar />
        <!-- Privacy Policy Section -->
        <div class="header-logo">
          <img class="header-shadow" src="../static/sha.png" />
          <div class="privacy-wrapper">
            <div class="privacy-content">
              <h1 class="privacy-title">Privacy Policy</h1>
              <p class="effective-date"><strong>Effective Date:</strong> 29/07/2024</p>

              <p class="intro-text">
                Kiva Stone ("Company," "we," "our," or "us") respects your privacy and is committed to protecting the personal information of our clients, partners, and website visitors. This Privacy Policy outlines the types of information we may collect, how we use it, and the safeguards we maintain to ensure compliance with applicable privacy and data protection laws.
              </p>

              <Section title="1. Information We Collect">
                <ul class="policy-list">
                  <li><strong>Information Provided by You:</strong> Such as your name, email, telephone, company info, etc.</li>
                  <li><strong>Automatically Collected Information:</strong> IP, browser type, device info, usage data.</li>
                  <li><strong>Cookies and Tracking Technologies:</strong> Used to enhance user experience and manage website functionality.</li>
                </ul>
              </Section>

              <Section title="2. Purpose of Collection and Use">
                <ul class="policy-list">
                  <li>Responding to inquiries & quotations</li>
                  <li>Managing and fulfilling requests</li>
                  <li>Optimizing website and services</li>
                  <li>System security & fraud prevention</li>
                  <li>Regulatory compliance</li>
                </ul>
                <p class="note-text">We do not sell or share your personal information for marketing purposes.</p>
              </Section>

              <Section title="3. Payments">
                <p class="section-text">Kiva Stone does not accept direct payments. All financial transactions are conducted exclusively through authorized invoicing and billing channels.</p>
              </Section>

              <Section title="4. Advertising">
                <p class="section-text">Kiva Stone does not engage in paid advertising and does not share customer information with advertisers.</p>
              </Section>

              <Section title="5. Disclosure of Information">
                <ul class="policy-list">
                  <li><strong>Service Providers:</strong> Trusted partners with confidentiality obligations.</li>
                  <li><strong>Legal Compliance:</strong> As required by law.</li>
                  <li><strong>Protection of Rights:</strong> To safeguard rights, property, or safety.</li>
                </ul>
              </Section>

              <Section title="6. Data Retention">
                <p class="section-text">We retain personal information only as long as necessary to fulfill the purposes outlined, comply with legal obligations, and resolve disputes.</p>
              </Section>

              <Section title="7. Security">
                <p class="section-text">We use industry-standard safeguards, but no transmission over the internet is 100% secure.</p>
              </Section>

              <Section title="8. Your Rights">
                <ul class="policy-list">
                  <li>Access your personal data</li>
                  <li>Request corrections</li>
                  <li>Request deletion (subject to law)</li>
                  <li>Restrict or object to processing</li>
                </ul>
              </Section>

              <Section title="9. Third-Party Websites">
                <p class="section-text">We are not responsible for third-party websites linked from our site. Review their privacy policies.</p>
              </Section>

              <Section title="10. Children's Privacy">
                <p class="section-text">Services are not directed toward individuals under 13, and we do not knowingly collect data from children.</p>
              </Section>

              <Section title="11. Updates to this Policy">
                <p class="section-text">Policy updates will be published on this page with a revised "Effective Date."</p>
              </Section>

              <Section title="12. Contact Information">
                <div class="contact-info">
                  <p><strong>Kiva Stone</strong></p>
                  <p>600 SW 12th Ave, Deerfield Beach, FL 33442, USA</p>
                  <p>📧 <strong>Email:</strong> info@kivastone.com</p>
                  <p>📞 <strong>Phone:</strong> +1 954 876 1235</p>
                </div>
              </Section>

            </div>
          </div>
        </div>
        <FooterSection />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  layout: "default",
  components: {
    NavBar: () => import("../components/NavBar.vue"),
    FooterSection: () => import("../components/FooterSection.vue"),
  },
  methods: {
    pageView(page) {
      location.href = `/${page}`;
    },
  },
};
</script>

<style scoped>
.header-logo {
  width: 100%;
  background-size: cover;
  background-position: center;
  min-height:120vh;
  position: relative;
  background-image: url("../static/coming-soon.png");
  padding: clamp(60px, 12vw, 100px) 0 clamp(40px, 8vw, 80px);
}

.header-shadow {
  position: absolute;
  left: 0;
  top: 0;
  z-index: 1;
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.privacy-wrapper {
  position: relative;
  z-index: 2;
  max-width: 900px;
  margin: 20vh auto 0 auto;
  padding: 0 clamp(15px, 4vw, 20px);
  width: 100%;
  box-sizing: border-box;
}

.privacy-content {
  background: rgba(255, 255, 255, 0.95);
  padding: clamp(30px, 6vw, 60px) clamp(20px, 5vw, 50px);
  border-radius: clamp(6px, 1vw, 8px);
  box-shadow: 0 10px 40px rgba(0, 0, 0, 0.3);
  color: #333;
  width: 100%;
  box-sizing: border-box;
  overflow-wrap: break-word;
  word-wrap: break-word;
}

.privacy-title {
  font-size: clamp(24px, 5vw, 42px);
  font-weight: bold;
  margin-bottom: clamp(15px, 3vw, 20px);
  text-align: center;
  color: #1a1a1a;
  font-family: "Nexa", sans-serif;
  letter-spacing: 1px;
  line-height: 1.2;
}

.effective-date {
  text-align: center;
  margin-bottom: clamp(20px, 4vw, 30px);
  font-size: clamp(12px, 2vw, 14px);
  color: #666;
}

.intro-text {
  margin-bottom: clamp(25px, 4vw, 35px);
  line-height: 1.8;
  text-align: left;
  font-size: clamp(14px, 2vw, 15px);
  color: #444;
  word-wrap: break-word;
  overflow-wrap: break-word;
  hyphens: auto;
}

.section-text {
  margin-bottom: clamp(12px, 2vw, 15px);
  line-height: 1.8;
  text-align: left;
  font-size: clamp(14px, 2vw, 15px);
  color: #444;
  word-wrap: break-word;
  overflow-wrap: break-word;
  hyphens: auto;
}

.note-text {
  margin-top: clamp(12px, 2vw, 15px);
  line-height: 1.8;
  text-align: left;
  font-size: clamp(14px, 2vw, 15px);
  color: #444;
  word-wrap: break-word;
  overflow-wrap: break-word;
  hyphens: auto;
}

.policy-list {
  list-style: disc;
  padding-left: clamp(20px, 3vw, 25px);
  margin-bottom: clamp(12px, 2vw, 15px);
  text-align: left;
}

.policy-list li {
  margin-bottom: clamp(10px, 2vw, 12px);
  line-height: 1.7;
  font-size: clamp(14px, 2vw, 15px);
  color: #444;
  word-wrap: break-word;
  overflow-wrap: break-word;
  hyphens: auto;
}

.contact-info {
  text-align: center;
  margin-top: clamp(15px, 3vw, 20px);
  padding: clamp(20px, 3vw, 25px);
  background: rgba(0, 0, 0, 0.03);
  border-radius: clamp(4px, 1vw, 6px);
}

.contact-info p {
  margin-bottom: clamp(6px, 1.5vw, 8px);
  line-height: 1.6;
  font-size: clamp(13px, 2vw, 15px);
  color: #444;
  word-break: break-word;
}

.coming-btn {
  padding: clamp(10px, 2vw, 12px) clamp(25px, 4vw, 35px);
  background: #000;
  color: #fff;
  display: inline-block;
  margin-top: clamp(30px, 5vw, 40px);
  font-size: clamp(10px, 1.5vw, 11px);
  cursor: pointer;
  font-family: "Nexa", sans-serif;
  letter-spacing: clamp(1px, 0.2vw, 1.5px);
  transition: all 0.3s ease;
  border: 2px solid #000;
  text-align: center;
  border-radius: 2px;
}

.coming-btn:hover {
  background: #fff;
  color: #000;
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.2);
}

/* Tablet optimizations */
@media only screen and (max-width: 768px) {
  .header-logo {
    min-height: auto;
  }
  
  .privacy-content {
    box-shadow: 0 6px 24px rgba(0, 0, 0, 0.25);
  }
}

/* Small mobile optimizations */
@media only screen and (max-width: 480px) {
  .privacy-wrapper {
    padding: 0 10px;
  }
  
  .privacy-content {
    padding: 25px 15px;
    border-radius: 4px;
  }
  
  .contact-info p {
    font-size: 13px;
  }
  
  .coming-btn {
    width: 100%;
    max-width: 280px;
  }
  
  .intro-text,
  .section-text,
  .note-text {
    font-size: 13px;
    line-height: 1.6;
  }
  
  .policy-list li {
    font-size: 13px;
    line-height: 1.6;
  }
}

/* Extra small devices */
@media only screen and (max-width: 360px) {
  .privacy-title {
    font-size: 22px;
  }
  
  .policy-list {
    padding-left: 18px;
  }
  
  .intro-text,
  .section-text,
  .note-text,
  .policy-list li {
    font-size: 13px;
  }
}

/* Large desktop optimizations */
@media only screen and (min-width: 1400px) {
  .privacy-wrapper {
    max-width: 1000px;
  }
}
</style>