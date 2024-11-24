<template>
  <div class="min-h-screen bg-gradient-to-b from-sky-50 to-white">
    <!-- Navigation -->
    <nav class="fixed top-0 left-0 right-0 bg-white/80 backdrop-blur-md z-50 border-b border-gray-100">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex justify-between items-center h-16">
          <!-- Logo -->
          <div class="flex-shrink-0">
            <a href="#" class="flex items-center">
              <svg class="h-8 w-8 text-sky-500" viewBox="0 0 600 601" fill="currentColor">
                <path
                  d="M599.999 489.5V485.59C600.003 483.073 599.009 480.658 597.234 478.873L468.851 350.511C465.655 347.316 463.12 343.522 461.391 339.348C459.661 335.173 458.771 330.698 458.771 326.179C458.771 321.661 459.661 317.186 461.391 313.011C463.12 308.837 465.655 305.043 468.851 301.848C472.046 298.653 475.839 296.118 480.014 294.389C484.188 292.659 488.663 291.769 493.182 291.769C497.701 291.769 502.175 292.659 506.35 294.389C510.525 296.118 514.318 298.653 517.513 301.848L583.822 368.135C585.148 369.458 586.836 370.358 588.672 370.722C590.509 371.087 592.413 370.899 594.143 370.183C595.874 369.467 597.353 368.254 598.395 366.698C599.438 365.142 599.996 363.312 599.999 361.44V71.5609C600 69.6863 599.445 67.8536 598.404 66.2944C597.364 64.7351 595.885 63.5192 594.153 62.8004C592.422 62.0815 590.517 61.892 588.678 62.2556C586.839 62.6193 585.149 63.5199 583.822 64.8436L271.782 376.883C270.899 377.762 270.198 378.807 269.719 379.958C269.241 381.109 268.994 382.343 268.994 383.589C268.994 384.836 269.241 386.07 269.719 387.221C270.198 388.372 270.899 389.417 271.782 390.296L347.508 466.022C350.704 469.217 353.238 473.01 354.968 477.185C356.697 481.359 357.587 485.834 357.587 490.353C357.587 494.872 356.697 499.346 354.968 503.521C353.238 507.696 350.704 511.489 347.508 514.684V514.684C344.314 517.882 340.522 520.419 336.347 522.15C332.172 523.881 327.697 524.772 323.177 524.772C318.657 524.772 314.182 523.881 310.007 522.15C305.832 520.419 302.039 517.882 298.846 514.684L223.12 438.958C221.339 437.184 218.927 436.188 216.414 436.188C213.9 436.188 211.488 437.184 209.707 438.958L64.7785 583.908C63.4548 585.236 62.5542 586.925 62.1905 588.764C61.8269 590.603 62.0164 592.509 62.7353 594.24C63.4541 595.971 64.67 597.451 66.2293 598.491C67.7885 599.532 69.6212 600.087 71.4958 600.086H489.413C503.935 600.088 518.315 597.228 531.732 591.669C545.148 586.11 557.336 577.961 567.601 567.688V567.688C577.874 557.423 586.023 545.234 591.582 531.818C597.142 518.402 600.002 504.022 599.999 489.5V489.5Z" />
              </svg>
              <span class="ml-2 text-xl font-bold text-gray-900">EduTour</span>
            </a>
          </div>

          <!-- Navigation Links -->
          <div class="hidden md:flex items-center space-x-8">
            <a href="#services" class="text-gray-600 hover:text-sky-500 transition-colors">Services</a>
            <a href="#destinations" class="text-gray-600 hover:text-sky-500 transition-colors">Destinations</a>
            <a href="#about" class="text-gray-600 hover:text-sky-500 transition-colors">About Us</a>
            <a href="#contact" class="text-gray-600 hover:text-sky-500 transition-colors">Contact</a>
          </div>

          <!-- CTA Button -->
          <div class="hidden md:block">
            <button @click="showBookNowModal = true"
              class="bg-sky-500 text-white px-6 py-2 rounded-full hover:bg-sky-600 transition-colors">
              Book Now
            </button>
          </div>

          <!-- Mobile Menu Button -->
          <div class="md:hidden">
            <button @click="toggleMobileMenu" class="text-gray-600 hover:text-gray-900">
              <MenuIcon v-if="!isMobileMenuOpen" class="h-6 w-6" />
              <XIcon v-else class="h-6 w-6" />
            </button>
          </div>
        </div>
      </div>

      <!-- Mobile Menu -->
      <div v-if="isMobileMenuOpen" class="md:hidden">
        <div class="px-2 pt-2 pb-3 space-y-1">
          <a href="#services" class="block px-3 py-2 text-gray-600">Services</a>
          <a href="#destinations" class="block px-3 py-2 text-gray-600">Destinations</a>
          <a href="#about" class="block px-3 py-2 text-gray-600">About Us</a>
          <a href="#contact" class="block px-3 py-2 text-gray-600">Contact</a>
          <button @click="showBookNowModal = true"
            class="w-full mt-2 bg-sky-500 text-white px-6 py-2 rounded-full hover:bg-sky-600">
            Book Now
          </button>
        </div>
      </div>
    </nav>

    <!-- Hero Section -->
    <section class="pt-32 pb-20 px-4 sm:px-6 lg:px-8">
      <div class="max-w-7xl mx-auto">
        <div class="text-center">
          <h1 class="text-4xl sm:text-5xl md:text-6xl font-bold text-gray-900 mb-6">
            Discover Educational Adventures
          </h1>
          <p class="text-xl text-gray-600 mb-8 max-w-2xl mx-auto">
            Experience meaningful school excursions without the hassle. We handle everything, so you can focus on what
            matters most - your students' growth.
          </p>
          <div class="flex flex-col sm:flex-row justify-center gap-4">
            <button @click="showPlanTourModal = true"
              class="bg-sky-500 text-white px-8 py-3 rounded-full hover:bg-sky-600 transition-colors">
              Plan Your Tour
            </button>
            <button @click="showLearnMoreModal = true"
              class="border border-gray-300 text-gray-700 px-8 py-3 rounded-full hover:bg-gray-50 transition-colors">
              Learn More
            </button>
          </div>
        </div>
      </div>
    </section>

    <!-- Services Section -->
    <section id="services" class="py-20 bg-gray-50">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <h2 class="text-3xl font-bold text-center mb-12">Our Services</h2>
        <div class="grid md:grid-cols-3 gap-8">
          <div class="bg-white p-6 rounded-xl shadow-sm">
            <MapIcon class="h-12 w-12 text-sky-500 mb-4" />
            <h3 class="text-xl font-semibold mb-2">Tour Planning</h3>
            <p class="text-gray-600">Comprehensive tour planning and itinerary development tailored to your curriculum.
            </p>
          </div>
          <div class="bg-white p-6 rounded-xl shadow-sm">
            <ShieldCheckIcon class="h-12 w-12 text-sky-500 mb-4" />
            <h3 class="text-xl font-semibold mb-2">Safety Management</h3>
            <p class="text-gray-600">Complete risk assessment and safety protocols for worry-free travel.</p>
          </div>
          <div class="bg-white p-6 rounded-xl shadow-sm">
            <BookOpenIcon class="h-12 w-12 text-sky-500 mb-4" />
            <h3 class="text-xl font-semibold mb-2">Educational Programs</h3>
            <p class="text-gray-600">Curriculum-aligned activities and learning materials for maximum educational value.
            </p>
          </div>
        </div>
      </div>
    </section>

    <!-- Destinations Section -->
    <section id="destinations" class="py-20">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <h2 class="text-3xl font-bold text-center mb-12">Popular Destinations</h2>
        <div class="grid md:grid-cols-3 gap-8">
          <div class="group relative overflow-hidden rounded-xl">
            <img src="https://placeholder.pics/svg/400x600" alt="Science Museum"
              class="w-full h-64 object-cover transition-transform group-hover:scale-110" />
            <div class="absolute inset-0 bg-gradient-to-t from-black/70 to-transparent flex items-end">
              <div class="p-6">
                <h3 class="text-xl font-bold text-white">Science Museums</h3>
                <p class="text-gray-200">Interactive learning experiences</p>
              </div>
            </div>
          </div>
          <div class="group relative overflow-hidden rounded-xl">
            <img src="https://placeholder.pics/svg/400x600" alt="Historical Sites"
              class="w-full h-64 object-cover transition-transform group-hover:scale-110" />
            <div class="absolute inset-0 bg-gradient-to-t from-black/70 to-transparent flex items-end">
              <div class="p-6">
                <h3 class="text-xl font-bold text-white">Historical Sites</h3>
                <p class="text-gray-200">Living history experiences</p>
              </div>
            </div>
          </div>
          <div class="group relative overflow-hidden rounded-xl">
            <img src="https://placeholder.pics/svg/400x600" alt="Nature Reserves"
              class="w-full h-64 object-cover transition-transform group-hover:scale-110" />
            <div class="absolute inset-0 bg-gradient-to-t from-black/70 to-transparent flex items-end">
              <div class="p-6">
                <h3 class="text-xl font-bold text-white">Nature Reserves</h3>
                <p class="text-gray-200">Environmental education programs</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- About Us Section -->
    <section id="about" class="py-20 bg-gray-50">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="grid md:grid-cols-2 gap-12 items-center">
          <div>
            <h2 class="text-3xl font-bold mb-6">About EduTour</h2>
            <p class="text-gray-600 mb-4">
              With over 10 years of experience in educational travel, EduTour has been helping schools create meaningful
              learning experiences outside the classroom.
            </p>
            <p class="text-gray-600 mb-4">
              Our team of experienced educators and travel professionals works tirelessly to ensure every tour is both
              educational and enjoyable.
            </p>
            <ul class="space-y-4">
              <li class="flex items-center">
                <CheckCircleIcon class="h-6 w-6 text-sky-500 mr-2" />
                <span>Certified tour guides with teaching background</span>
              </li>
              <li class="flex items-center">
                <CheckCircleIcon class="h-6 w-6 text-sky-500 mr-2" />
                <span>Customizable itineraries for all grade levels</span>
              </li>
              <li class="flex items-center">
                <CheckCircleIcon class="h-6 w-6 text-sky-500 mr-2" />
                <span>24/7 support during tours</span>
              </li>
            </ul>
          </div>
          <div class="relative">
            <img src="https://placeholder.pics/svg/600x800" alt="About Us" class="rounded-xl shadow-lg" />
          </div>
        </div>
      </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="py-20">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <h2 class="text-3xl font-bold text-center mb-12">Contact Us</h2>
        <div class="grid md:grid-cols-2 gap-12">
          <div>
            <form class="space-y-6">
              <div>
                <label class="block text-sm font-medium text-gray-700 mb-1">Name</label>
                <input type="text"
                  class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-sky-500 focus:border-sky-500" />

              </div>
              <div>
                <label class="block text-sm font-medium text-gray-700 mb-1">Email</label>
                <input type="email"
                  class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-sky-500 focus:border-sky-500" />
              </div>
              <div>
                <label class="block text-sm font-medium text-gray-700 mb-1">Message</label>
                <textarea rows="4"
                  class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-sky-500 focus:border-sky-500"></textarea>
              </div>
              <button type="submit"
                class="w-full bg-sky-500 text-white px-6 py-3 rounded-lg hover:bg-sky-600 transition-colors">
                Send Message
              </button>
            </form>
          </div>
          <div class="space-y-6">
            <div>
              <h3 class="text-xl font-semibold mb-4">Get in Touch</h3>
              <p class="text-gray-600">Have questions about our educational tours? We're here to help!</p>
            </div>
            <div>
              <h4 class="font-semibold mb-2">Office Hours</h4>
              <p class="text-gray-600">Monday - Friday: 9:00 AM - 5:00 PM</p>
              <p class="text-gray-600">Saturday: 10:00 AM - 2:00 PM</p>
            </div>
            <div>
              <h4 class="font-semibold mb-2">Contact Information</h4>
              <div class="space-y-2">
                <p class="flex items-center text-gray-600">
                  <MapPinIcon class="h-5 w-5 mr-2" />
                  123 Education St, Learning City, ED 12345
                </p>
                <p class="flex items-center text-gray-600">
                  <PhoneIcon class="h-5 w-5 mr-2" />
                  +1 (555) 123-4567
                </p>
                <p class="flex items-center text-gray-600">
                  <MailIcon class="h-5 w-5 mr-2" />
                  info@edutour.com
                </p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Footer -->
    <footer class="bg-gray-900 text-white py-12">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="grid md:grid-cols-4 gap-8">
          <div>
            <h3 class="text-xl font-bold mb-4">EduTour</h3>
            <p class="text-gray-400">Making educational travel accessible and meaningful for schools across the country.
            </p>
          </div>
          <div>
            <h4 class="font-semibold mb-4">Quick Links</h4>
            <ul class="space-y-2">
              <li><a href="#" class="text-gray-400 hover:text-white">Home</a></li>
              <li><a href="#services" class="text-gray-400 hover:text-white">Services</a></li>
              <li><a href="#destinations" class="text-gray-400 hover:text-white">Destinations</a></li>
              <li><a href="#about" class="text-gray-400 hover:text-white">About</a></li>
              <li><a href="#contact" class="text-gray-400 hover:text-white">Contact</a></li>
            </ul>
          </div>
          <div>
            <h4 class="font-semibold mb-4">Contact</h4>
            <ul class="space-y-2 text-gray-400">
              <li>info@edutour.com</li>
              <li>+1 (555) 123-4567</li>
              <li>123 Education St</li>
              <li>Learning City, ED 12345</li>
            </ul>
          </div>
          <div>
            <h4 class="font-semibold mb-4">Follow Us</h4>
            <div class="flex space-x-4">
              <a href="#" class="text-gray-400 hover:text-white">
                <FacebookIcon class="h-6 w-6" />
              </a>
              <a href="#" class="text-gray-400 hover:text-white">
                <TwitterIcon class="h-6 w-6" />
              </a>
              <a href="#" class="text-gray-400 hover:text-white">
                <InstagramIcon class="h-6 w-6" />
              </a>
              <a href="#" class="text-gray-400 hover:text-white">
                <LinkedinIcon class="h-6 w-6" />
              </a>
            </div>
          </div>
        </div>
        <div class="mt-12 pt-8 border-t border-gray-800 text-center text-gray-400">
          <p>&copy; {{ new Date().getFullYear() }} EduTour. All rights reserved.</p>
        </div>
      </div>
    </footer>

    <!-- Modals -->
    <!-- Book Now Modal -->
    <Transition name="modal">
      <div v-if="showBookNowModal" class="fixed inset-0 z-50 overflow-y-auto" role="dialog" aria-modal="true">
        <div
          class="flex items-end sm:items-center justify-center min-h-screen pt-4 px-4 pb-20 text-center sm:block sm:p-0">
          <div class="fixed inset-0 bg-gray-500 bg-opacity-75 transition-opacity" @click="showBookNowModal = false">
          </div>
          <div
            class="relative inline-block align-bottom bg-white rounded-lg px-4 pt-5 pb-4 text-left overflow-hidden shadow-xl transform transition-all sm:my-8 sm:align-middle sm:max-w-lg sm:w-full sm:p-6">
            <div class="absolute top-0 right-0 pt-4 pr-4">
              <button @click="showBookNowModal = false" class="text-gray-400 hover:text-gray-500">
                <XIcon class="h-6 w-6" />
              </button>
            </div>
            <div class="sm:flex sm:items-start">
              <div class="mt-3 text-center sm:mt-0 sm:text-left w-full">
                <h3 class="text-lg font-medium leading-6 text-gray-900 mb-4">Book Your Tour</h3>
                <form class="space-y-4">
                  <div>
                    <label class="block text-sm font-medium text-gray-700">School Name</label>
                    <input type="text"
                      class="mt-1 block w-full border-gray-300 rounded-md shadow-sm focus:ring-sky-500 focus:border-sky-500 sm:text-sm" />
                  </div>
                  <div>
                    <label class="block text-sm font-medium text-gray-700">Contact Person</label>
                    <input type="text"
                      class="mt-1 block w-full border-gray-300 rounded-md shadow-sm focus:ring-sky-500 focus:border-sky-500 sm:text-sm" />
                  </div>
                  <div>
                    <label class="block text-sm font-medium text-gray-700">Email</label>
                    <input type="email"
                      class="mt-1 block w-full border-gray-300 rounded-md shadow-sm focus:ring-sky-500 focus:border-sky-500 sm:text-sm" />
                  </div>
                  <div>
                    <label class="block text-sm font-medium text-gray-700">Preferred Date</label>
                    <input type="date"
                      class="mt-1 block w-full border-gray-300 rounded-md shadow-sm focus:ring-sky-500 focus:border-sky-500 sm:text-sm" />
                  </div>
                  <div>
                    <label class="block text-sm font-medium text-gray-700">Number of Students</label>
                    <input type="number"
                      class="mt-1 block w-full border-gray-300 rounded-md shadow-sm focus:ring-sky-500 focus:border-sky-500 sm:text-sm" />
                  </div>
                  <div class="mt-5 sm:mt-4 sm:flex sm:flex-row-reverse">
                    <button type="submit"
                      class="w-full inline-flex justify-center rounded-md border border-transparent shadow-sm px-4 py-2 bg-sky-500 text-base font-medium text-white hover:bg-sky-600 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-sky-500 sm:ml-3 sm:w-auto sm:text-sm">
                      Submit Booking
                    </button>
                    <button type="button" @click="showBookNowModal = false"
                      class="mt-3 w-full inline-flex justify-center rounded-md border border-gray-300 shadow-sm px-4 py-2 bg-white text-base font-medium text-gray-700 hover:bg-gray-50 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-sky-500 sm:mt-0 sm:w-auto sm:text-sm">
                      Cancel
                    </button>
                  </div>
                </form>
              </div>
            </div>
          </div>
        </div>
      </div>
    </Transition>

    <!-- Plan Tour Modal -->
    <Transition name="modal">
      <div v-if="showPlanTourModal" class="fixed inset-0 z-50 overflow-y-auto" role="dialog" aria-modal="true">
        <div
          class="flex items-end sm:items-center justify-center min-h-screen pt-4 px-4 pb-20 text-center sm:block sm:p-0">
          <div class="fixed inset-0 bg-gray-500 bg-opacity-75 transition-opacity" @click="showPlanTourModal = false">
          </div>
          <div
            class="relative inline-block align-bottom bg-white rounded-lg px-4 pt-5 pb-4 text-left overflow-hidden shadow-xl transform transition-all sm:my-8 sm:align-middle sm:max-w-lg sm:w-full sm:p-6">
            <div class="absolute top-0 right-0 pt-4 pr-4">
              <button @click="showPlanTourModal = false" class="text-gray-400 hover:text-gray-500">
                <XIcon class="h-6 w-6" />
              </button>
            </div>
            <div class="sm:flex sm:items-start">
              <div class="mt-3 text-center sm:mt-0 sm:text-left w-full">
                <h3 class="text-lg font-medium leading-6 text-gray-900 mb-4">Plan Your Educational Tour</h3>
                <form class="space-y-4">
                  <div>
                    <label class="block text-sm font-medium text-gray-700">Destination Type</label>
                    <select
                      class="mt-1 block w-full border-gray-300 rounded-md shadow-sm focus:ring-sky-500 focus:border-sky-500 sm:text-sm">
                      <option>Science Museums</option>
                      <option>Historical Sites</option>
                      <option>Nature Reserves</option>
                      <option>Cultural Centers</option>
                    </select>
                  </div>
                  <div>
                    <label class="block text-sm font-medium text-gray-700">Duration (Days)</label>
                    <input type="number" min="1" max="14"
                      class="mt-1 block w-full border-gray-300 rounded-md shadow-sm focus:ring-sky-500 focus:border-sky-500 sm:text-sm" />
                  </div>
                  <div>
                    <label class="block text-sm font-medium text-gray-700">Grade Level</label>
                    <select
                      class="mt-1 block w-full border-gray-300 rounded-md shadow-sm focus:ring-sky-500 focus:border-sky-500 sm:text-sm">
                      <option>Elementary School</option>
                      <option>Middle School</option>
                      <option>High School</option>
                    </select>
                  </div>
                  <div>
                    <label class="block text-sm font-medium text-gray-700">Special Requirements</label>
                    <textarea rows="3"
                      class="mt-1 block w-full border-gray-300 rounded-md shadow-sm focus:ring-sky-500 focus:border-sky-500 sm:text-sm"></textarea>
                  </div>
                  <div class="mt-5 sm:mt-4 sm:flex sm:flex-row-reverse">
                    <button type="submit"
                      class="w-full inline-flex justify-center rounded-md border border-transparent shadow-sm px-4 py-2 bg-sky-500 text-base font-medium text-white hover:bg-sky-600 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-sky-500 sm:ml-3 sm:w-auto sm:text-sm">
                      Submit Plan
                    </button>
                    <button type="button" @click="showPlanTourModal = false"
                      class="mt-3 w-full inline-flex justify-center rounded-md border border-gray-300 shadow-sm px-4 py-2 bg-white text-base font-medium text-gray-700 hover:bg-gray-50 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-sky-500 sm:mt-0 sm:w-auto sm:text-sm">
                      Cancel
                    </button>
                  </div>
                </form>
              </div>
            </div>
          </div>
        </div>
      </div>
    </Transition>

    <!-- Learn More Modal -->
    <Transition name="modal">
      <div v-if="showLearnMoreModal" class="fixed inset-0 z-50 overflow-y-auto" role="dialog" aria-modal="true">
        <div
          class="flex items-end sm:items-center justify-center min-h-screen pt-4 px-4 pb-20 text-center sm:block sm:p-0">
          <div class="fixed inset-0 bg-gray-500 bg-opacity-75 transition-opacity" @click="showLearnMoreModal = false">
          </div>
          <div
            class="relative inline-block align-bottom bg-white rounded-lg px-4 pt-5 pb-4 text-left overflow-hidden shadow-xl transform transition-all sm:my-8 sm:align-middle sm:max-w-lg sm:w-full sm:p-6">
            <div class="absolute top-0 right-0 pt-4 pr-4">
              <button @click="showLearnMoreModal = false" class="text-gray-400 hover:text-gray-500">
                <XIcon class="h-6 w-6" />
              </button>
            </div>
            <div class="sm:flex sm:items-start">
              <div class="mt-3 text-center sm:mt-0 sm:text-left">
                <h3 class="text-lg font-medium leading-6 text-gray-900 mb-4">About Our Educational Tours</h3>
                <div class="space-y-4">
                  <div>
                    <h4 class="font-medium text-gray-900">Our Mission</h4>
                    <p class="text-gray-500">To provide enriching educational experiences through carefully planned and
                      executed school tours that complement classroom learning.</p>
                  </div>
                  <div>
                    <h4 class="font-medium text-gray-900">Why Choose Us?</h4>
                    <ul class="mt-2 space-y-2">
                      <li class="flex items-start">
                        <CheckIcon class="h-5 w-5 text-sky-500 mr-2 mt-0.5" />
                        <span class="text-gray-500">Expert educational tour planners</span>
                      </li>
                      <li class="flex items-start">
                        <CheckIcon class="h-5 w-5 text-sky-500 mr-2 mt-0.5" />
                        <span class="text-gray-500">Curriculum-aligned activities</span>
                      </li>
                      <li class="flex items-start">
                        <CheckIcon class="h-5 w-5 text-sky-500 mr-2 mt-0.5" />
                        <span class="text-gray-500">Comprehensive safety measures</span>
                      </li>
                      <li class="flex items-start">
                        <CheckIcon class="h-5 w-5 text-sky-500 mr-2 mt-0.5" />
                        <span class="text-gray-500">Flexible booking options</span>
                      </li>
                    </ul>
                  </div>
                  <div>
                    <h4 class="font-medium text-gray-900">Get Started</h4>
                    <p class="text-gray-500">Ready to plan your educational tour? Contact our team for a personalized
                      consultation.</p>
                  </div>
                </div>
                <div class="mt-5 sm:mt-4 sm:flex sm:flex-row-reverse">
                  <button type="button" @click="showLearnMoreModal = false"
                    class="w-full inline-flex justify-center rounded-md border border-gray-300 shadow-sm px-4 py-2 bg-white text-base font-medium text-gray-700 hover:bg-gray-50 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-sky-500 sm:ml-3 sm:w-auto sm:text-sm">
                    Close
                  </button>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </Transition>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import {
  MenuIcon,
  XIcon,
  MapIcon,
  ShieldCheckIcon,
  BookOpenIcon,
  FacebookIcon,
  TwitterIcon,
  InstagramIcon,
  LinkedinIcon,
  CheckCircleIcon,
  MapPinIcon,
  PhoneIcon,
  MailIcon,
  CheckIcon
} from 'lucide-vue-next'

const isMobileMenuOpen = ref(false)
const showBookNowModal = ref(false)
const showPlanTourModal = ref(false)
const showLearnMoreModal = ref(false)

const toggleMobileMenu = () => {
  isMobileMenuOpen.value = !isMobileMenuOpen.value
}
</script>

<style>
@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(20px);
  }

  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.fade-in {
  animation: fadeIn 0.5s ease-out forwards;
}

.modal-enter-active,
.modal-leave-active {
  transition: opacity 0.3s ease;
}

.modal-enter-from,
.modal-leave-to {
  opacity: 0;
}
</style>