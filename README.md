# About

NaGCal is a way to keep your on call schedule in Google Calendar and look up
contact details to the person who is currently on call from Google Contacts.
It was built for use with Nagios, the network monitoring system.

# How to install

It should be fairly easy to install NaGCal. These are the general steps:

1. Download a release
2. Run python setup.py install to download dependencies
3. Copy the example configuration file to your config directory
4. Run nagcal --sync to set up authentication tokens with Google's APIs

When this is done, you can use the provided mail-to-oncall script as a
notification command in Nagios. It has been written to behave like /bin/mail,
with the exception that it sends email to the currently on call person if
there is one. If there is noone on call or an error occurs, it sends mail
to the address that was provided as an argument instead.

## Dependencies

NaGCal is written in Python and depends on a few other Python packages.
Running python setup.py install should download and install these for you.

- gdata
- iso8601
- httplib2
- oauth2client
- python-gflags
