<!-- © 2026 Iheb Zmerli. Template ID: {{ uniqueId }}. Unauthorized use prohibited. -->
<template>
  <div class="preview" :class="{ 'dark-mode': isDarkMode }">
    <!-- OUTER CADRE - Full signature wrapper -->
    <table
      role="presentation"
      cellpadding="0"
      cellspacing="0"
      border="0"
      width="670"
      style="
        border-collapse: collapse;
        width: 670px;
        max-width: 100%;
        font-family: Poppins, Arial, sans-serif;
        line-height: 1.2;
        border: 2px solid;
        border-radius: 16px;
        overflow: hidden;
      "
      :style="{ borderColor: companyColor }"
    >
      <tbody>
        <tr>
          <td style="padding: 20px">
            <!-- MAIN SIGNATURE TABLE with border -->
            <table
              role="presentation"
              cellpadding="0"
              cellspacing="0"
              border="0"
              width="670"
              style="
                border-collapse: collapse;
                width: 670px;
                max-width: 100%;
                font-family: Poppins, Arial, sans-serif;
                line-height: 1.2;
                border: 2px solid;
                border-radius: 16px;
                overflow: hidden;
                margin: 0 auto;
              "
              :style="{ borderColor: companyColor }"
            >
              <tbody>
                <tr class="main-signature-row">
                  <!-- LEFT SIDE - Solid brand color background -->
                  <td
                    style="
                      padding: 16px 12px;
                      vertical-align: top;
                      width: 450px;
                      background-color: #f5f5f5;
                      border-right: 2px dotted;
                      position: relative;
                      overflow: hidden;
                    "
                    :style="{
                      backgroundColor: companyColorBgLeft,
                      borderRightColor: companyColor,
                    }"
                  >
                    <div style="padding: 5px 5px 5px 10px">
                      <!-- NAME -->
                      <div
                        class="signature-name"
                        style="
                          font-family: Georgia, serif;
                          font-weight: 500;
                          font-size: 30px;
                          color: #1a1a1a;
                          margin-bottom: 20px;
                          letter-spacing: -0.5px;
                          white-space: nowrap;
                          overflow: hidden;
                          text-overflow: ellipsis;
                          text-transform: uppercase;
                        "
                        :style="{ color: companyColor }"
                      >
                        {{ name }}
                      </div>

                      <!-- JOB with rounded pill background -->
                      <div
                        class="signature-job"
                        style="
                          font-size: 15px;
                          margin-bottom: 20px;
                          color: #000;
                          font-family: 'Poppins', Arial, sans-serif;
                          font-weight: 500;
                          display: inline-block;
                          padding: 5px 14px;
                          border-radius: 25px;
                          letter-spacing: 0.3px;
                        "
                        :style="{ backgroundColor: companyColor + '40' }"
                      >
                        {{ jobTitle }}
                      </div>

                      <!-- DIVIDER -->
                      <div
                        style="
                          height: 1px;
                          background: linear-gradient(
                            90deg,
                            #ddd 0%,
                            transparent 100%
                          );
                          margin: 10px 0 25px 0;
                        "
                        :style="{
                          background:
                            'linear-gradient(90deg, ' +
                            companyColor +
                            '40 0%, transparent 100%)',
                        }"
                      ></div>

                      <!-- PHONES -->
                      <table
                        role="presentation"
                        cellpadding="0"
                        cellspacing="0"
                        border="0"
                        style="margin-bottom: 30px"
                      >
                        <tbody>
                          <tr>
                            <td style="width: 28px; vertical-align: middle">
                              <table
                                role="presentation"
                                cellpadding="0"
                                cellspacing="0"
                                border="0"
                              >
                                <tbody>
                                  <tr>
                                    <td
                                      align="center"
                                      valign="middle"
                                      style="
                                        width: 26px;
                                        height: 26px;
                                        background-color: #e8e8e8;
                                        border-radius: 50%;
                                      "
                                      :style="{ backgroundColor: companyColor }"
                                    >
                                      <img
                                        src="https://raw.githubusercontent.com/ihebZmez/signature-generator/main/public/images-template-icons/v2_10.png"
                                        width="13"
                                        height="13"
                                        style="
                                          display: block;
                                          border: 0;
                                          margin: 0 auto;
                                        "
                                      />
                                    </td>
                                  </tr>
                                </tbody>
                              </table>
                            </td>
                            <td
                              v-if="office"
                              style="
                                padding-left: 10px;
                                font-size: 12px;
                                color: #333;
                                font-family: 'Poppins', Arial, sans-serif;
                              "
                            >
                              <a :href="'tel:' + office" style="color: inherit; text-decoration: none;">{{ office }}</a>
                            </td>
                            <td
                              v-if="office && mobile"
                              style="
                                padding: 0 4px;
                                font-size: 12px;
                                color: #999;
                              "
                            >
                              |
                            </td>
                            <td
                              v-if="mobile"
                              style="
                                font-size: 12px;
                                color: #333;
                                font-family: 'Poppins', Arial, sans-serif;
                              "
                            >
                              <a :href="'tel:' + mobile" style="color: inherit; text-decoration: none;">{{ mobile }}</a>
                            </td>
                            <td
                              v-if="post"
                              style="
                                font-size: 12px;
                                color: #333;
                                font-family: 'Poppins', Arial, sans-serif;
                              "
                            >
                              &nbsp;|&nbsp; Post :&nbsp;<a :href="'tel:' + post" style="color: inherit; text-decoration: none;">{{ post }}</a>
                            </td>
                          </tr>
                        </tbody>
                      </table>

                      <!-- WEBSITE -->
                      <table
                        role="presentation"
                        cellpadding="0"
                        cellspacing="0"
                        border="0"
                        style="margin-bottom: 30px"
                      >
                        <tbody>
                          <tr>
                            <td style="width: 28px; vertical-align: middle">
                              <a :href="company.url" target="_blank" rel="noopener noreferrer" style="text-decoration: none; display: inline-block;">
                                <table
                                  role="presentation"
                                  cellpadding="0"
                                  cellspacing="0"
                                  border="0"
                                >
                                  <tbody>
                                    <tr>
                                      <td
                                        align="center"
                                        valign="middle"
                                        style="
                                          width: 26px;
                                          height: 26px;
                                          background-color: #e8e8e8;
                                          border-radius: 50%;
                                        "
                                        :style="{ backgroundColor: companyColor }"
                                      >
                                        <img
                                          src="https://raw.githubusercontent.com/ihebZmez/signature-generator/main/public/images-template-icons/v2_11.png"
                                          width="13"
                                          height="13"
                                          style="
                                            display: block;
                                            border: 0;
                                            margin: 0 auto;
                                          "
                                        />
                                      </td>
                                    </tr>
                                  </tbody>
                                </table>
                              </a>
                            </td>
                            <td
                              style="
                                padding-left: 10px;
                                font-size: 12px;
                                color: #333;
                                font-family: 'Poppins', Arial, sans-serif;
                              "
                            >
                              <a
                                :href="company.url"
                                target="_blank"
                                rel="noopener noreferrer"
                                style="color: inherit; text-decoration: none"
                              >
                                {{ companyUrlReadable }}
                              </a>
                            </td>
                          </tr>
                        </tbody>
                      </table>

                      <!-- ADDRESS -->
                      <a :href="'https://maps.google.com/?q=' + encodeURIComponent(companyAddressText)" target="_blank" rel="noopener noreferrer" style="text-decoration: none; display: inline-block;">
                        <table
                          role="presentation"
                          cellpadding="0"
                          cellspacing="0"
                          border="0"
                        >
                          <tbody>
                            <tr>
                              <td style="width: 28px; vertical-align: top">
                                <table
                                  role="presentation"
                                  cellpadding="0"
                                  cellspacing="0"
                                  border="0"
                                >
                                  <tbody>
                                    <tr>
                                      <td
                                        align="center"
                                        valign="middle"
                                        style="
                                          width: 26px;
                                          height: 26px;
                                          background-color: #e8e8e8;
                                          border-radius: 50%;
                                        "
                                        :style="{ backgroundColor: companyColor }"
                                      >
                                        <img
                                          src="https://raw.githubusercontent.com/ihebZmez/signature-generator/main/public/images-template-icons/v2_13.png"
                                          width="13"
                                          height="13"
                                          style="
                                            display: block;
                                            border: 0;
                                            margin: 0 auto;
                                          "
                                        />
                                      </td>
                                    </tr>
                                  </tbody>
                                </table>
                              </td>
                              <td
                                style="
                                  padding-left: 10px;
                                  font-size: 12px;
                                  font-family: 'Poppins', Arial, sans-serif;
                                  line-height: 1.4;
                                "
                                :style="{ color: isDarkMode ? '#ffffff' : '#555555' }"
                              >
                                <span v-html="companyAddress"></span>
                              </td>
                            </tr>
                          </tbody>
                        </table>
                      </a>
                    </div>
                  </td>

                  <!-- RIGHT SIDE - Subtle gray background (survives dark mode) -->
                  <td
                    style="
                      vertical-align: top;
                      width: 260px;
                      text-align: center;
                      padding: 10px 12px 16px 12px;
                      background-color: #fafafa;
                      position: relative;
                      overflow: hidden;
                    "
                    :style="{ backgroundColor: companyColorBgRight }"
                  >
                    <!-- Configurable spacer div -->
                    <div :style="{ margin: divRightTopMargin }"></div>

                    <!-- LOGO -->
                    <div :style="{ margin: logoMargin }">
                      <a 
                        :href="company.url" 
                        target="_blank" 
                        rel="noopener noreferrer" 
                        style="display: block; text-decoration: none;"
                      >
                        <img
                          :src="companyLogo"
                          :alt="company.name"
                          :style="logoStyle"
                          style="max-width: 100%; height: auto; display: block; margin: 0 auto;"
                        />
                      </a>
                    </div>

                    <!-- DIVIDER -->
                    <div
                      style="
                        height: 1px;
                        background: #e0e0e0;
                        margin: 15px 0px;
                      "
                      :style="{ background: companyColor + '30' }"
                    ></div>

                    <!-- SOCIAL ICONS -->
                    <table
                      role="presentation"
                      cellpadding="0"
                      cellspacing="0"
                      border="0"
                      align="center"
                      style="margin: 15px auto 10px auto;"
                    >
                      <tbody>
                        <tr>
                          <td
                            v-for="(icon, index) in socialIcons"
                            :key="icon.link"
                            style="padding-right: 10px; vertical-align: middle;"
                            :style="{ paddingRight: index === socialIcons.length - 1 ? '0px' : '10px' }"
                          >
                            <a
                              :href="icon.link"
                              target="_blank"
                              rel="noopener noreferrer"
                              style="text-decoration: none; display: inline-block;"
                            >
                              <table
                                role="presentation"
                                cellpadding="0"
                                cellspacing="0"
                                border="0"
                              >
                                <tbody>
                                  <tr>
                                    <td
                                      align="center"
                                      valign="middle"
                                      style="
                                        width: 34px;
                                        height: 34px;
                                        background-color: #e8e8e8;
                                        border-radius: 50%;
                                        transition: all 0.2s ease;
                                      "
                                      :style="{ backgroundColor: companyColor }"
                                    >
                                      <img
                                        :src="icon.img"
                                        :alt="icon.alt"
                                        width="20"
                                        height="20"
                                        style="
                                          display: block;
                                          border: 0;
                                          margin: 0 auto;
                                        "
                                      />
                                    </td>
                                  </tr>
                                </tbody>
                              </table>
                            </a>
                          </td>
                        </tr>
                      </tbody>
                    </table>

                    <!-- BOTTOM SECTION - POWERED BY + QR CODE stacked -->
                    <div style="margin-top: 20px;">
                      <!-- POWERED BY LOGO -->
                      <img
                        v-if="form.showPoweredBy"
                        src="https://raw.githubusercontent.com/ihebZmez/signature-generator/main/public/logo/v1_2_poweredByCfac.png"
                        :style="poweredByLogoStyle"
                        style="
                          border: 0;
                          display: block;
                          opacity: 0.8;
                          margin: 0 auto;
                        "
                      />

                      <!-- QR CODE SECTION - Dynamic vCard QR -->
                      <div style="text-align: center; margin-top: 1px;">
                        <div style="
                          display: inline-block;
                          border-radius: 16px;
                        " :style="{ borderColor: companyColor }">
                          <img 
                            v-if="form.showVCardQR && vCardQRCode"
                            :src="vCardQRCode"
                            alt="vCard QR Code - Scan to save contact"
                            :style="vCardQRCodeStyle"
                            style="
                              display: block;
                              border-radius: 0px;
                            "
                            :key="qrGenerationKey"
                          />
                          <div 
                            v-else-if="form.showVCardQR && !vCardQRCode"
                            style="width:50px;height:50px;background:#f0f0f0;display:flex;align-items:center;justify-content:center;font-size:8px;color:#999;"
                          >
                            Loading...
                          </div>
                          <img 
                            v-if="form.showQrCodeWebsite"
                            src="https://raw.githubusercontent.com/ihebZmez/signature-generator/main/public/qr.png"
                            alt="QR Code"
                            :style="qrCodeStyle"
                            style="
                              display: block;
                              border-radius: 4px;
                            "
                          />
                          <img 
                            v-if="form.showQrCodeRateus"
                            src="https://raw.githubusercontent.com/ihebZmez/signature-generator/main/public/qrRateus.png"
                            alt="QR Rateus"
                            :style="qrCodeStyle"
                            style="
                              display: block;
                              border-radius: 4px;
                            "
                          />
                        </div>
                      </div>
                    </div>
                  </td>
                </tr>
              </tbody>
            </table>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import QRCode from 'qrcode';

export default {
  name: "SignaturePreview",
  props: ["companies", "form", "isDarkMode"],

  data() {
    return {
      vCardQRCode: null,
      qrGenerationKey: 0 // Force re-render when changed
    };
  },

  computed: {
    company() {
      return this.companies.find((c) => c.name === this.form.company) || {};
    },

    companyColor() {
      return this.company.color || "#6f4e37";
    },

    companyColorBgLeft() {
      return this.company.colorBgLeft || "#e8c458";
    },

    companyColorBgRight() {
      return this.company.colorBgRight || "#ab9f20";
    },

    companyLogo() {
      return this.company.logo;
    },
    
    divRightTopMargin() {
      return (this.company && this.company.divRightTopMargin) || "0px";
    },

    logoStyle() {
      const width = this.company.logoWidthBg || 170;
      const height = this.company.logoHeightBg || "auto";
      const margin = this.company.logoMarginBg || "10px auto 5px auto";

      const style = {
        border: "0",
        display: "block",
        margin: margin,
      };

      if (typeof width === "number" || !isNaN(parseFloat(width))) {
        style.width = typeof width === "number" ? width + "px" : width;
      } else {
        style.width = width;
      }

      if (height && height !== "auto") {
        if (typeof height === "number" || !isNaN(parseFloat(height))) {
          style.height = typeof height === "number" ? height + "px" : height;
        } else {
          style.height = height;
        }
      } else {
        style.height = "auto";
      }

      return style;
    },

    poweredByLogoStyle() {
      return {
        width: "140px",
        minWidth: "140px",
        maxWidth: "140px",
        height: "20px",
        objectFit: "contain"
      };
    },

    qrCodeStyle() {
      return {
        width: "31px",
        minWidth: "31px",
        maxWidth: "31px",
        height: "31px"
      };
    },

    vCardQRCodeStyle() {
      return {
        width: "145px",
        minWidth: "145px",
        maxWidth: "145px",
        height: "145px"
      };
    },
        
    socialIconsMarginBg() {
      return this.company.socialIconsMarginBg || "20px 0px 40px 0px";
    },
    
    companyUrlReadable() {
      return (this.company.url || "").replace(/(^\w+:|^)\/\//, "");
    },

    name() {
      return this.form.name?.trim() || "First Last";
    },

    jobTitle() {
      return this.form.jobTitle?.trim() || "Job Title";
    },

    office() {
      return this.form.office || "";
    },

    mobile() {
      return this.form.mobile || "";
    },

    post() {
      return this.form.post || "";
    },

    companyAddress() {
      const value =
        this.form.companyAddress?.trim() || this.company.address || "";
      return value.replace(/\s{2,}/g, "<br>");
    },

    companyAddressText() {
      return this.form.companyAddress?.trim() || this.company.address || "";
    },

    // Generate vCard string in version 3.0 format with proper encoding
    vCardString() {
      const name = this.name || "";
      const jobTitle = this.jobTitle || "";
      const companyName = this.company.name || "";
      const office = this.office || "";
      const mobile = this.mobile || "";
      const post = this.post || "";
      const email = this.company.email || "";

      // Skip if no useful data
      if (!name && !jobTitle && !companyName && !office && !mobile && !post && !email) {
        return null;
      }

      // Split name into first and last
      const nameParts = name.trim().split(' ');
      const lastName = nameParts.pop() || '';
      const firstName = nameParts.join(' ') || '';

      let vCard = 'BEGIN:VCARD\r\n';
      vCard += 'VERSION:3.0\r\n';
      vCard += `FN:${this.escapeVCardString(name)}\r\n`;
      vCard += `N:${this.escapeVCardString(lastName)};${this.escapeVCardString(firstName)};;;\r\n`;
      
      if (jobTitle) vCard += `TITLE:${this.escapeVCardString(jobTitle)}\r\n`;
      if (companyName) vCard += `ORG:${this.escapeVCardString(companyName)}\r\n`;
      if (office) vCard += `TEL;TYPE=WORK,VOICE:${office}\r\n`;
      if (mobile) vCard += `TEL;TYPE=CELL,VOICE:${mobile}\r\n`;
      if (post) vCard += `TEL;TYPE=WORK;X-SUBTYPE=Post:${post}\r\n`;
      if (email) vCard += `EMAIL;TYPE=WORK:${email}\r\n`;
      
      vCard += 'REV:' + new Date().toISOString().replace(/[-:]/g, '').split('.')[0] + 'Z\r\n';
      vCard += 'END:VCARD\r\n';

      console.log('Generated vCard:', vCard); // Debug log
      return vCard;
    },

    socialIcons() {
      const icons = [
        {
          link: this.company.socialIcons?.instagram || "#",
          img: "https://raw.githubusercontent.com/ihebZmez/signature-generator/main/public/images-template-icons/v1_4.png",
          alt: "Instagram",
        },
        {
          link: this.company.socialIcons?.fb || "#",
          img: "https://raw.githubusercontent.com/ihebZmez/signature-generator/main/public/images-template-icons/v1_5.png",
          alt: "Facebook",
        },
        {
          link: this.company.socialIcons?.tiktok || "#",
          img: "https://raw.githubusercontent.com/ihebZmez/signature-generator/main/public/images-template-icons/v1_6.png",
          alt: "TikTok",
        },
        {
          link: this.company.socialIcons?.linkedin || "#",
          img: "https://raw.githubusercontent.com/ihebZmez/signature-generator/main/public/images-template-icons/v1_7.png",
          alt: "LinkedIn",
        },
      ];

      return icons.filter(
        (icon) =>
          icon.link && icon.link.trim() !== "#" && icon.link.trim() !== "",
      );
    },
  },

  watch: {
    // Watch all relevant data sources
    'form.name': {
      handler() { this.regenerateQRCode(); },
      deep: true
    },
    'form.jobTitle': {
      handler() { this.regenerateQRCode(); },
      deep: true
    },
    'form.office': {
      handler() { this.regenerateQRCode(); },
      deep: true
    },
    'form.mobile': {
      handler() { this.regenerateQRCode(); },
      deep: true
    },
    'form.post': {
      handler() { this.regenerateQRCode(); },
      deep: true
    },
    'form.company': {
      handler() { 
        setTimeout(() => this.regenerateQRCode(), 100);
      },
      deep: true
    },
    'form.showVCardQR': {
      handler(newVal) {
        if (newVal) {
          this.regenerateQRCode();
        } else {
          this.vCardQRCode = null;
        }
      },
      immediate: true
    },
    company: {
      handler() {
        this.regenerateQRCode();
      },
      deep: true
    }
  },

  mounted() {
    this.regenerateQRCode();
  },

  methods: {
    escapeVCardString(str) {
      if (!str) return '';
      // Escape special characters in vCard
      return String(str).replace(/[;, \\"]/g, function(match) {
        if (match === ';') return '\\;';
        if (match === ',') return '\\,';
        if (match === '\\') return '\\\\';
        if (match === '"') return '\\"';
        return match;
      });
    },

    async regenerateQRCode() {
      if (!this.form.showVCardQR) {
        this.vCardQRCode = null;
        return;
      }

      // Small delay to ensure all data is updated
      await this.$nextTick();
      
      const vCardData = this.vCardString;
      
      if (!vCardData || vCardData === 'BEGIN:VCARD\r\nVERSION:3.0\r\nEND:VCARD\r\n') {
        console.log('No vCard data to generate');
        this.vCardQRCode = null;
        return;
      }

      try {
        // Force a new key to ensure re-render
        this.qrGenerationKey++;
        
        const qrCodeDataURL = await QRCode.toDataURL(vCardData, {
          errorCorrectionLevel: 'H', // High error correction for better scanning
          margin: 2,
          width: 200,
          type: 'image/png',
          color: {
            dark: '#000000',
            light: '#FFFFFF'
          }
        });
        
        this.vCardQRCode = qrCodeDataURL;
        console.log('vCard QR Code generated successfully');
      } catch (error) {
        console.error('Error generating vCard QR code:', error);
        this.vCardQRCode = null;
      }
    }
  }
};
</script>

<style>
@import url("https://fonts.cdnfonts.com/css/poppins");
@import url("https://fonts.cdnfonts.com/css/georgia");

/* ─── MANUAL DARK MODE TOGGLE ─── */
.preview.dark-mode .signature-name,
.preview.dark-mode .signature-job,
.preview.dark-mode td:not([style*="border-radius: 50%"]),
.preview.dark-mode span:not([style*="border-radius: 50%"]),
.preview.dark-mode a {
  color: #ffffff !important;
}

.preview.dark-mode td[style*="background-color: #f5f5f5"],
.preview.dark-mode td[style*="background-color: #fafafa"] {
  background-color: #2a2a2a !important;
}

/* DO NOTHING to circular icons - keep them exactly as they are */
/* No styles for td[style*="border-radius: 50%"] in dark mode */

/* ─── GMAIL DARK MODE ─── */
@media (prefers-color-scheme: dark) {
  td[style*="background-color: #f5f5f5"],
  td[style*="background-color: #fafafa"] {
    background-color: #2a2a2a !important;
    -webkit-print-color-adjust: exact;
    print-color-adjust: exact;
  }

  .signature-name,
  .signature-job,
  td[style*="color: #333"],
  td[style*="color: #555"],
  td[style*="color: #1a1a1a"] {
    color: #ffffff !important;
  }

  /* DO NOTHING to circular icons in Gmail dark mode either */
  /* No styles for td[style*="border-radius: 50%"] here */

  img {
    filter: none !important;
  }
}

/* ─── MOBILE ─── */
/* Fix for long names on mobile */
@media screen and (max-width: 480px) {
  .powered-by-logo {
    width: 100px !important;
    height: auto !important;
    max-width: 100% !important;
  }
  table[width="670"] {
    width: 100% !important;
  }

  td[style*="width: 450px"] {
    width: 60% !important;
    display: block !important;
    width: 100% !important;
  }

  td[style*="width: 260px"] {
    width: 100% !important;
    display: block !important;
  }

  .signature-name {
    font-size: 18px !important;
    white-space: normal !important;
    word-wrap: break-word !important;
    line-height: 1.2 !important;
    margin-bottom: 8px !important;
  }

  /* Make left side stack on top on mobile */
  .preview .main-signature-row {
    display: flex;
    flex-direction: column;
  }

  .preview table tbody tr td:first-child {
    border-right: none !important;
    border-bottom: 2px dotted;
    border-bottom-color: v-bind(companyColor);
    border-radius: 16px 16px 0 0 !important;
  }

  .preview table tbody tr td:last-child {
    border-radius: 0 0 16px 16px !important;
  }

  /* Adjust social icons on mobile */
  .preview td[style*="margin: 20px 0px 40px 70px"] {
    margin: 15px auto !important;
    text-align: center !important;
  }
}
</style>