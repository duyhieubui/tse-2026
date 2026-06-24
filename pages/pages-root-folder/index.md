---
#
# Use the widgets beneath and the content will be
# inserted automatically in the webpage. To make
# this work, you have to use › layout: frontpage
#
layout: frontpage
header:
  image_fullwidth: header_drop.jpg
widget1:
  title: "Call for Papers"
  url: '/cfp/'
  text: '!SITE_DESCRIPTION! will be held in !SITE_LOCATION!.<br/><br/>'
widget2:
  title: "Important dates"
  url: '/authors/dates/'
  text: "<em>Full-paper Submission: !SUBMISSION_DATE!</em><br/><em>Notification of acceptance: !ACCEPTANCE_DATE!</em> <br/>	<em>Camera-ready submission: !CAMERA_READY_DATE!</em><br/><em>Advance registration: !ADVANCE_REG!</em><br/><br/>"
widget3:
  title: "Visa & Travel"
  url: 'https://www.vietnamairlines.com/nz/en/travel-information/travel-advice/for-flights-to-Vietnam'
  text: 'Non-Vietnamese nationals are required to obtain a visa to enter Vietnam. Non-Vietnamese passengers can apply for a visa or an electronic visa (e-visa) to save time. Some nationalities can enter Vietnam without a visa under certain conditions.'
#
# Use the call for action to show a button on the frontpage
#
# To make internal links, just use a permalink like this
# url: /getting-started/
#
# To style the button in different colors, use no value
# to use the main color or success, alert or secondary.
# To change colors see sass/_01_settings_colors.scss
#
callforaction:
  url: https://submission-link
  text: Submit your paper now!
  style: alert
permalink: /index.html
#
# This is a nasty hack to make the navigation highlight
# this page as active in the topbar navigation
#
homepage: true
---
