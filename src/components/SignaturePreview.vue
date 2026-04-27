<template>
  <div class="preview">
    <table
      role="presentation"
      cellpadding="0"
      cellspacing="0"
      border="0"
      style="
        border-collapse: collapse;
        width: 700px;
        max-width: 100%;
        font-family: Poppins, Arial, sans-serif;
        color: #231f20;
        line-height: 1.2;
      "
    >
      <tr>
        <!-- LEFT SIDE -->
        <td style="padding: 8px 10px; vertical-align: top; width: 260px">
          
          <!-- NAME -->
          <div
            style="
              font-family: 'Brittany Signature', cursive;
              font-size: 30px;
              color: #000;
              width: 216px;
              height: 65px;
            "
          >
            {{ name }}
          </div>

          <!-- JOB -->
          <div
            style="
              font-size: 11px;
              margin-top: -10px;
              font-family: Poppins;
            "
          >
            {{ jobTitle }}
          </div>

          <!-- PHONES -->
          <table style="margin-top: 10px">
            <tr>
              <td style="width: 20px">
                <span class="icon">
                  <img src="https://raw.githubusercontent.com/ihebZm/generateur-signature-cfac-erp/main/images-template-icons/v2_10.png" />
                </span>
              </td>
              <td class="text">{{ office }}</td>
              <td class="sep">|</td>
              <td class="text">{{ mobile }}</td>
            </tr>
          </table>

          <!-- WEBSITE -->
          <table style="margin-top: 10px">
            <tr>
              <td style="width: 20px">
                <span class="icon">
                  <img src="https://raw.githubusercontent.com/ihebZm/generateur-signature-cfac-erp/main/images-template-icons/v2_11.png" />
                </span>
              </td>
              <td class="text">
                {{ companyUrlReadable }}
              </td>
            </tr>
          </table>

          <!-- ADDRESS -->
          <table style="margin-top: 10px">
            <tr>
              <td style="width: 20px; vertical-align: top">
                <span class="icon">
                  <img src="https://raw.githubusercontent.com/ihebZm/generateur-signature-cfac-erp/main/images-template-icons/v2_12.png" />
                </span>
              </td>
              <td class="text">
                {{ companyAddress }}
              </td>
            </tr>
          </table>

        </td>

        <!-- RIGHT SIDE -->
        <td
          style="
            vertical-align: top;
            width: 300px;
            text-align: center;
            padding: 7px 0;
          "
        >
          <!-- LOGO -->
          <img
            :src="companyLogo"
            style="
              width: 170px;
              display: block;
              margin: 20px auto 0;
            "
          />

          <!-- SOCIAL -->
          <table align="center" style="margin-top: 8px">
            <tr>
              <td v-for="icon in socialIcons" :key="icon.link" style="padding-right: 9px">
                <a :href="icon.link" target="_blank">
                  <span class="social">
                    <img :src="icon.img" />
                  </span>
                </a>
              </td>
            </tr>
          </table>

        </td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  name: "SignaturePreview",
  props: ["companies", "form"],

  computed: {
    company() {
      return this.companies.find(c => c.name === this.form.company) || {};
    },

    companyLogo() {
      return this.company.logo;
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

    companyAddress() {
      return (this.company.address || "");
    },

    socialIcons() {
      return [
        {
          link: "https://www.instagram.com/kibocommunication",
          img: "https://raw.githubusercontent.com/ihebZm/generateur-signature-cfac-erp/main/images-template-icons/v1_4.png"
        },
        {
          link: "https://www.facebook.com/kibocommunication",
          img: "https://raw.githubusercontent.com/ihebZm/generateur-signature-cfac-erp/main/images-template-icons/v1_5.png"
        },
        {
          link: "https://www.tiktok.com/@kibocommunication",
          img: "https://raw.githubusercontent.com/ihebZm/generateur-signature-cfac-erp/main/images-template-icons/v1_6.png"
        },
        {
          link: "https://fr.linkedin.com/company/kibo-communication",
          img: "https://raw.githubusercontent.com/ihebZm/generateur-signature-cfac-erp/main/images-template-icons/v1_7.png"
        }
      ];
    }
  }
};
</script>

<style>
@import url('https://fonts.cdnfonts.com/css/brittany-signature');
@import url('https://fonts.cdnfonts.com/css/poppins');

.icon {
  display: inline-block;
  width: 14px;
  height: 14px;
  background: #ff3131;
  border-radius: 50%;
  position: relative;
}

.icon img {
  position: absolute;
  top: 50%;
  left: 50%;
  width: 11px;
  transform: translate(-50%, -50%);
}

.social {
  display: inline-block;
  width: 30px;
  height: 30px;
  background: #ff3131;
  border-radius: 50%;
  position: relative;
}

.social img {
  position: absolute;
  top: 2px;
  left: 2px;
  width: 26px;
}

.text {
  padding-left: 10px;
  font-size: 8px;
}

.sep {
  padding: 0 10px;
  font-size: 8px;
}
</style>