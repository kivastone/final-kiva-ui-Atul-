<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-12 px-0">
        <NavBar />

        <!-- Terms & Conditions Section -->
        <div class="header-logo">
          <img class="header-shadow" src="../static/sha.png" />
          <div class="privacy-wrapper">
            <div class="privacy-content">
              <h1 class="privacy-title">Terms & Conditions</h1>
              <p class="effective-date"><strong>Effective Date:</strong> 29/07/2024</p>

              <p class="intro-text">
                Welcome to Kiva Stone (“Company,” “we,” “our,” or “us”). By accessing or using our website (kivastone.com) and related services (collectively, the “Services”), you agree to comply with and be bound by these Terms & Conditions (“Terms”). If you do not agree with these Terms, you should not use our Services.
              </p>

              <Section title="1. Use of Our Website">
                <ul class="policy-list">
                  <li>You must use this website only for lawful purposes and in compliance with all applicable laws and regulations.</li>
                  <li>You agree not to engage in any activity that may disrupt or interfere with the proper functioning of the website.</li>
                  <li>Unauthorized attempts to access, modify, or interfere with our systems or data are strictly prohibited.</li>
                </ul>
              </Section>

              <Section title="2. Intellectual Property">
                <ul class="policy-list">
                  <li>All content on this website, including but not limited to text, images, graphics, logos, designs, product listings, and software, is the property of Kiva Stone or its licensors and is protected by copyright, trademark, and other intellectual property laws.</li>
                  <li>You may not copy, reproduce, distribute, or otherwise exploit any content from this website without our prior written permission.</li>
                </ul>
              </Section>

              <Section title="3. Products and Services">
                <ul class="policy-list">
                  <li>The materials displayed on this website are for informational purposes only and do not constitute binding offers.</li>
                  <li>Product availability, specifications, and descriptions are subject to change at any time without prior notice.</li>
                  <li>Quotations or proposals provided are valid only for the period specified therein.</li>
                </ul>
              </Section>

              <Section title="4. Payments">
                <p class="section-text">
                  Kiva Stone does not accept direct payments under any circumstances. All payments must be made exclusively through our authorized invoicing and billing channels. We will never request payment details (such as bank information, credit card numbers, or digital wallet credentials) via email, phone, or messaging platforms. Any such request should be treated as unauthorized and reported to us immediately.
                </p>
              </Section>

              <Section title="5. Advertising">
                <p class="section-text">
                  Kiva Stone does not engage in paid advertising or promotional listings. Any advertisement or marketing material representing Kiva Stone without written authorization should be considered invalid and unauthorized.
                </p>
              </Section>

              <Section title="6. Disclaimer of Warranties">
                <p class="section-text">
                  This website and its content are provided “as is” and “as available,” without warranties of any kind, either express or implied. We make no guarantees regarding the accuracy, reliability, or completeness of the information provided. To the fullest extent permitted by law, Kiva Stone disclaims all warranties, express or implied, including but not limited to implied warranties of merchantability, fitness for a particular purpose, and non-infringement.
                </p>
              </Section>

              <Section title="7. Limitation of Liability">
                <p class="section-text">
                  To the maximum extent permitted by law, Kiva Stone shall not be liable for any direct, indirect, incidental, consequential, or punitive damages arising from or related to your use of the website or services. This includes, but is not limited to, damages for loss of data, business interruption, or loss of profits.
                </p>
              </Section>

              <Section title="8. Third-Party Links">
                <p class="section-text">
                  Our website may contain links to external websites for your convenience. Kiva Stone is not responsible for the content, accuracy, or practices of any third-party websites, and inclusion of such links does not imply endorsement.
                </p>
              </Section>

              <Section title="9. Indemnification">
                <p class="section-text">
                  You agree to indemnify, defend, and hold harmless Kiva Stone, its officers, employees, and affiliates from and against any claims, liabilities, damages, losses, or expenses (including reasonable attorney’s fees) arising out of or related to your violation of these Terms or misuse of our Services.
                </p>
              </Section>

              <Section title="10. Governing Law">
                <p class="section-text">
                  These Terms shall be governed by and construed in accordance with the laws of the State of Florida, United States, without regard to its conflict of law principles.
                </p>
              </Section>

              <Section title="11. Modifications to Terms">
                <p class="section-text">
                  We reserve the right to update, modify, or replace these Terms at any time. Any changes will be posted on this page with the revised “Effective Date.” Continued use of the Services after such changes constitutes acceptance of the updated Terms.
                </p>
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
  min-height: 100vh;
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
  margin: 15vh auto 0 auto;
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