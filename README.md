![Raspberry Shake event logo](https://raw.githubusercontent.com/raspishake/rsudp/master/docs/_static/logo.png)
# rsudp
### Continuous sudden motion and visual monitoring of Raspberry Shake data
*Written by Ian Nesbitt (@iannesbitt) and Richard Boaz (@ivor)*

[![PyPI](https://img.shields.io/pypi/v/rsudp)](https://pypi.org/project/rsudp/)
[![PyPI - Downloads](https://img.shields.io/pypi/dm/rsudp)](https://pypi.org/project/rsudp/)
[![GitHub](https://img.shields.io/github/license/raspishake/rsudp)](https://github.com/raspishake/rsudp/blob/master/LICENSE)
[![Documentation](https://img.shields.io/badge/docs-passed-brightgreen)](https://raspishake.github.io/rsudp/)
[![Build Status](https://scrutinizer-ci.com/g/raspishake/rsudp/badges/build.png?b=master)](https://scrutinizer-ci.com/g/raspishake/rsudp/build-status/master)
[![Code Coverage](https://scrutinizer-ci.com/g/raspishake/rsudp/badges/coverage.png?b=master)](https://scrutinizer-ci.com/g/raspishake/rsudp/?branch=master)
[![Scrutinizer Code Quality](https://scrutinizer-ci.com/g/raspishake/rsudp/badges/quality-score.png?b=master)](https://scrutinizer-ci.com/g/raspishake/rsudp/?branch=master)
[![JOSS Publication Status](https://joss.theoj.org/papers/11e2afeb2d45da49b4092e8311c8f8a4/status.svg)](https://joss.theoj.org/papers/11e2afeb2d45da49b4092e8311c8f8a4)

`rsudp` is a tool for receiving and interacting with data casts from [Raspberry Shake](https://raspberryshake.org) personal seismographs and Raspberry Boom pressure transducer instruments.

`rsudp` has [full documentation here](https://raspishake.github.io/rsudp/). We also have [tutorial instructions](https://raspishake.github.io/rsudp/index.html#tutorial) to install, set up, and run rsudp there. Additionally, our documentation features [YouTube walkthroughs](https://raspishake.github.io/rsudp/youtube.html), [notes for contributors](https://raspishake.github.io/rsudp/contributing.html), a brief [Developer's guide](https://raspishake.github.io/rsudp/theory.html), and [module documentation](https://raspishake.github.io/rsudp/#code-documentation).

`rsudp` contains ten main features:
1. **Alert** - an earthquake/sudden motion alert trigger, complete with a bandpass filter and stream deconvolution capabilities
2. **AlertSound** - a thread that plays a MP3 audio file in the event of the alert module signalling an alarm state
3. **Plot** - a live-plotting routine to display data as it arrives on the port, with an option to save plots some time after an alarm
4. **Tweeter** - a thread that broadcasts a Twitter message when the alert module is triggered, and optionally can tweet saved plots from the plot module
5. **Telegrammer** - a thread similar to the Tweeter module that sends a [Telegram](https://telegram.org) message when an alarm is triggered, which can also broadcast saved images
6. **Writer** - a simple miniSEED writer
7. **Forward** - forward a data cast to one or several IP/port destinations
8. **RSAM** - computes RSAM (Real-time Seismic AMplitude) and either prints or forwards it to an IP/port destination
9. **Custom** - run custom code when an `ALARM` message is received
10. **Print** - a debugging tool to output raw data to the command line

`rsudp` is written in Python but requires no coding knowledge to run. Simply follow the [instructions to install the software](https://raspishake.github.io/rsudp/installing.html), go to your Shake's web front end, [configure a UDP datacast](https://manual.raspberryshake.org/udp.html#configuring-a-data-stream-the-easy-way) to your computer's local IP address, [start the software](https://raspishake.github.io/rsudp/running.html) from the command line, and watch the data roll in.

![Earthquake plot recorded on a Raspberry Shake 4D](https://raw.githubusercontent.com/raspishake/rsudp/master/docs/_static/4d-event.png)

(Above) a plot of an earthquake on the four channels of a Raspberry Shake 4D (EHZ---the geophone channel, and EHE, EHN, and ENZ---the accelerometer east, north, and vertical channels).
