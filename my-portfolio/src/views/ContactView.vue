<script setup>
// Static form posting directly to Formspree — no Vue state needed here.
// Formspree will handle submission and redirect the user to a thank-you page.
</script>

<template>
  <main>
    <section class="contact-section">
      <h1>Contact Me</h1>
      <p>Feel free to reach out by filling out the form below.</p>

      <form action="https://formspree.io/f/mpqnvozl" method="POST">
        <div>
          <label for="name">Name:</label>
          <input type="text" id="name" name="name" required placeholder="Your Name" />
        </div>
        <div>
          <label for="email">Email:</label>
          <input
            type="email"
            id="email"
            name="email"
            required
            placeholder="your.email@example.com"
          />
        </div>
        <div>
          <label for="message">Message:</label>
          <textarea
            id="message"
            name="message"
            rows="5"
            required
            placeholder="Write your message here..."
          ></textarea>
        </div>
        <button type="submit">Send Message</button>
      </form>
    </section>

    <section class="social-media-section">
      <h2>Connect with Me</h2>
      <p>You can also find me on these platforms:</p>
      <ul class="social-media-list">
        <li>
          <a
            class="social-btn"
            href="https://www.linkedin.com/in/karah-fisher/"
            target="_blank"
            rel="noopener"
          >
            LinkedIn
          </a>
        </li>
        <li>
          <a
            class="social-btn"
            href="https://github.com/Karah-Fisher"
            target="_blank"
            rel="noopener"
          >
            GitHub
          </a>
        </li>
      </ul>
    </section>
  </main>
</template>
