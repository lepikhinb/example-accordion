<script setup lang="ts">
import Accordion from "./components/Accordion.vue"
</script>

<template>
  <div class="relative flex min-h-screen w-screen justify-center overflow-hidden md:pt-32 lg:pt-56">
    <img
      class="absolute left-0 top-0 h-screen w-[300%] max-w-none object-cover md:w-[200%] lg:w-full"
      src="@/images/bg.png" />

    <div class="relative w-full max-w-3xl p-12">
      <div class="grid gap-4 md:gap-6">
        <Accordion>
          <template #title> How to protect your personal information? </template>

          <p>
            You are in control of how much information you share on Twitter or any other website. Don’t post information
            you consider to be private, and be thoughtful about when you want to publicly share your location.
          </p>
          <p>
            Be wary of any communication that asks for your private contact information, personal information, or
            passwords. If you are ever unsure before you Tweet, we recommend you ask yourself the following questions:
          </p>
          <ul>
            <li>Who am I sharing this information with?</li>
            <li>How much and what type of information am I sharing?</li>
            <li>How many people can see the information I am sharing?</li>
            <li>Can I trust all the people that see this information?</li>
          </ul>
        </Accordion>

        <Accordion>
          <template #title> How to share and watch videos on Twitter? </template>

          <p>
            Record: You can record, edit and share videos from the Twitter app (Twitter for iPhone or Twitter for
            Android OS 4.1 and higher).
          </p>
          <p>Import: If you use the Twitter for iPhone or iPad app, you can import videos from your device.</p>
          <p>Upload: You can upload videos to twitter.com.</p>
          <p>Go live: Learn how to create a live video right from your Twitter app.</p>
        </Accordion>

        <Accordion>
          <template #title> How to Tweet? </template>

          <p>
            Type your Tweet (up to 280 characters) into the compose box at the top of your Home timeline, or select the
            Tweet button in the navigation bar.
          </p>
          <p>You can include up to 4 photos, a GIF, or a video in your Tweet.</p>
          <p>Select the Tweet button to post the Tweet to your profile.</p>
        </Accordion>

        <Accordion>
          <template #title> How to add your phone number to your account </template>

          <p>Click the More icon and select Settings and privacy from the drop-down menu.</p>
          <p>Click on Your account tab and choose Account information.</p>
          <p>Select Phone from the drop-down menu.</p>
          <p>
            Click Add phone number and verify your password. No need to include your country code or leading zero; we
            handle these automatically. Click Continue.
          </p>
          <p>
            We will send a code (via SMS text message) to your phone number. Enter it in the Verification code box and
            click Activate phone.
          </p>
        </Accordion>
      </div>
    </div>
  </div>
</template>
