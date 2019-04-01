---
layout: workshop      # DON'T CHANGE THIS.
carpentry: "swc"    # what kind of Carpentry (must be either "lc" or "dc" or "swc").  
                      # Be sure to update the Carpentry type in _config.yml as well.  
venue: "Introduction to High Performance Computing (HPC) <br>Griffith University"        # brief name of host site without address (e.g., "Euphoric State University")
address: "G40_4.111 Gold Coast Campus"      # full street address of workshop (e.g., "Room A, 123 Forth Street, Blimingen, Euphoria")
country: "Australia"      # lowercase two-letter ISO country code such as "fr" (see https://en.wikipedia.org/wiki/ISO_3166-1)
language: "en"     # lowercase two-letter ISO language code such as "fr" (see https://en.wikipedia.org/wiki/ISO_639-1)
latlng: "-27.960345, 153.378868"       # decimal latitude and longitude of workshop venue (e.g., "41.7901128,-87.6007318" - use https://www.latlong.net/)
humandate: "18 April"    # human-readable dates for the workshop (e.g., "Feb 17-18, 2020")
humantime: "10:00am to 1:20pm"    # human-readable times for the workshop (e.g., "9:00 am - 4:30 pm")
startdate: 2019-04-18      # machine-readable start date for the workshop in YYYY-MM-DD format like 2015-01-01
enddate: 2019-04-18        # machine-readable end date for the workshop in YYYY-MM-DD format like 2015-01-02
instructor: ["Indy Siva"] # boxed, comma-separated list of instructors' names as strings, like ["Kay McNulty", "Betty Jennings", "Betty Snyder"]
helper: ["Amanda Miotto"]     # boxed, comma-separated list of helpers' names, like ["Marlyn Wescoff", "Fran Bilas", "Ruth Lichterman"]
email: ["hackyhour@griffith.edu.au"]    # boxed, comma-separated list of contact email addresses for the host, lead instructor, or whoever else is handling questions, like ["marlyn.wescoff@example.org", "fran.bilas@example.org", "ruth.lichterman@example.org"]
collaborative_notes:             # optional: URL for the workshop collaborative notes, e.g. an Etherpad or Google Docs document
eventbrite:           # optional: alphanumeric key for Eventbrite registration, e.g., "1234567890AB" (if Eventbrite is being used)
---

{% comment %} See instructions in the comments below for how to edit specific sections of this workshop template. {% endcomment %}

{% comment %}
  HEADER

  Edit the values in the block above to be appropriate for your workshop.
  If the value is not 'true', 'false', 'null', or a number, please use
  double quotation marks around the value, unless specified otherwise.
  And run 'make workshop-check' *before* committing to make sure that changes are good.
{% endcomment %}



<h2 id="general">General Information</h2>

{% comment %}
  INTRODUCTION

  Edit the general explanatory paragraph below if you want to change
  the pitch.
{% endcomment %}
{% if page.carpentry == "swc" %}
  {% include sc/intro.html %}
{% elsif page.carpentry == "dc" %}
  {% include dc/intro.html %}
{% elsif page.carpentry == "lc" %}
  {% include lc/intro.html %}
{% endif %}

{% comment %}
  AUDIENCE

  Explain who your audience is.  (In particular, tell readers if the
  workshop is only open to people from a particular institution.
{% endcomment %}
{% if page.carpentry == "swc" %}
  {% include sc/who.html %}
{% elsif page.carpentry == "dc" %}
  {% include dc/who.html %}
{% elsif page.carpentry == "lc" %}
  {% include lc/who.html %}
{% endif %}

{% comment %}
  LOCATION

  This block displays the address and links to maps showing directions
  if the latitude and longitude of the workshop have been set.  You
  can use https://itouchmap.com/latlong.html to find the lat/long of an
  address.
{% endcomment %}
{% if page.latlng %}
<p id="where">
  <strong>Where:</strong>
  {{page.address}}.
  Get directions with
  <a href="//www.openstreetmap.org/?mlat={{page.latlng | replace:',','&mlon='}}&zoom=16">OpenStreetMap</a>
  or
  <a href="//maps.google.com/maps?q={{page.latlng}}">Google Maps</a>.
</p>
{% endif %}

{% comment %}
  DATE

  This block displays the date and links to Google Calendar.
{% endcomment %}
{% if page.humandate %}
<p id="when">
  <strong>When:</strong>
  {{page.humandate}}.
  {% include workshop_calendar.html %}
</p>
{% endif %}

{% comment %}
  SPECIAL REQUIREMENTS

  Modify the block below if there are any special requirements.
{% endcomment %}
<p id="requirements">
  <strong>Requirements:</strong> Participants must bring a laptop with a
  Mac, Linux, or Windows operating system (not a tablet, Chromebook, etc.) that they have administrative privileges
  on. They should have a few specific software packages installed (listed
  <a href="#setup">below</a>). They are also required to abide by
  {% if page.carpentry == "swc" %}
  Software Carpentry's
  {% elsif page.carpentry == "dc" %}
  Data Carpentry's
  {% elsif page.carpentry == "lc" %}
  Library Carpentry's
  {% endif %}
  <a href="{{site.swc_site}}/conduct.html">Code of Conduct</a>.
</p>

{% comment %}
  ACCESSIBILITY

  Modify the block below if there are any barriers to accessibility or
  special instructions.
{% endcomment %}
<p id="accessibility">
  <strong>Accessibility:</strong> We are committed to making this workshop
  accessible to everybody.
  The workshop organizers have checked that:
</p>
<ul>
  <li>The room is wheelchair / scooter accessible.</li>
  <li>Accessible restrooms are available.</li>
</ul>
<p>
  Materials will be provided in advance of the workshop and
  large-print handouts are available if needed by notifying the
  organizers in advance.  If we can help making learning easier for
  you (e.g. sign-language interpreters, lactation facilities) please
  get in touch (using contact details below) and we will
  attempt to provide them.
</p>

{% comment %}
  CONTACT EMAIL ADDRESS

  Display the contact email address set in the configuration file.
{% endcomment %}
<p id="contact">
  <strong>Contact</strong>:
  Please email
  {% if page.email %}
    {% for email in page.email %}
      {% if forloop.last and page.email.size > 1 %}
        or
      {% else %}
        {% unless forloop.first %}
        ,
        {% endunless %}
      {% endif %}
      <a href='mailto:{{email}}'>{{email}}</a>
    {% endfor %}
  {% else %}
    to-be-announced
  {% endif %}
  for more information.
</p>

<hr/>


# Lesson Details: High Performance Computing 

All lessons [can be found here](https://amandamiotto.github.io/INTRO_HPC/) 

## Prior Experience

This workshop will be done entirely on the console using Bash. If you are not familiar with Bash, there is an [introductory session as part of our Python workshop](https://bio-swc-bne.github.io/2019-04-15-GriffithUni-Python/) on Monday at Nathan campus. You are welcome to come along to the Bash segment and skip the Python/Git if you like. If you cannot make that, please log into Lynda.com through the State Library of Queensland and [complete this course](https://www.lynda.com/Linux-tutorials/Learning-Linux-Command-Line/753913-2.html?srchtrk=index%3a1%0alinktypeid%3a2%0aq%3alinux+commands%0apage%3a1%0as%3arelevance%0asa%3atrue%0aproducttypeid%3a2)

You will need a basic understanding of the bash/linux terminal for this workshop.

## HPC Access

You will need to have an HPC user account before the workshop begins.  

Please create an account (if you don't already have one) on QRISCloud HPC Awoonga, you [can sign up here](https://rcc.uq.edu.au/awoonga). Please ensure you have registered for your account **ATLEAST 3 DAYS PRIOR** to the commencement of the workshop. It will be free for any Griffith University or QCIF member.

## Example Files

You will find the example [files used in this tutorial here.](https://github.com/amandamiotto/INTRO_HPC/raw/gh-pages/files/hpcCarpentry.zip)


## SSH

In order to connect to a remote computer, such as an HPC cluster.  Students will need an 'SSH' client on their computer;
check for your operating system below for instructions to download an SSH Client of your own.

**Windows**

Install [PuTTY Client](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html), ensure you pick the appropriate 32 or 64 bit edition.

**macOS**

OSx comes pre-isntalled with an SSH Client, access it via your terminal.

**Linux**

Linux OS comes pre-isntalled with an SSH Client, access it via your terminal.

## STFP

GUI tools to make transferring files easier.

**All OS**

[WinSCP](https://winscp.net/eng/download.php) is a Graphical Program used to transfer files between your computer and a remote HPC setup.
WinSCP can be used on Windows 7 and Windows 10.

If you are on a MacOS- [Cyberduck](https://cyberduck.io/) can be used as well.

You can also use Filezilla however it does come with lots of bloatware. 


