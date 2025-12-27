<script>
import aboutImg from "../assets/about4.jpg";
export default {
  name: "TheAbout",
  components: {},
  data() {
    return {
      aboutImg: aboutImg,
    };
  },
};
</script>
<style></style>
<template>
  <div className="py-10 text-white bg-[#232325] h-auto" id="about">
    <div
      className="flex md:flex-row flex-col-reverse items-center md:gap-5 px-4 md:px-12 max-w-6xl mx-auto"
    >
      <div>
        <div className="p-2">
          <div className="text-gray-300 my-3">
            <h3 className="text-4xl font-semibold mb-5">
              About <span>Me</span>
            </h3>
            <p
              className="text-justify leading-7 mx-auto text-[13px] md:text-[14px]"
            >
              I'm a Software Engineer with hands-on experience in Shopware, React, Vue, and PHP, specializing in the development of scalable, maintainable, and user-focused web applications. Strong problem-solving skills with a practical approach to building efficient solutions. Experienced in collaborating within cross-functional teams, adapting to new technologies, and continuously improving code quality to deliver reliable, high-impact products.
            </p>
          </div>
        </div>

        <div className="flex mt-10 items-center md:gap-7 gap-1 my-2">
          <div className="bg-[#333333]/40 lg:p-5 p-[27px] rounded-lg">
            <h3 className="md:text-4xl text-2xl font-semibold text-white">
              4
              <span>+</span>
            </h3>
            <p><span className="md:text-base text-xs">Projects</span></p>
          </div>
          <div className="bg-[#333333]/40 lg:p-5 p-[27px] rounded-lg">
            <h3 className="md:text-4xl text-2xl font-semibold text-white">
              2
              <span>+</span>
            </h3>
            <p>
              <span className="md:text-base text-xs">years experience</span>
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
