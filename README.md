# qw
This rcfile is elliptic's DCSS bot "qw", the first (and thus far only) bot
to win DCSS with no human assistance. A substantial amount of code here was
contributed by elliott or borrowed from N78291's bot "xw", and many others
have contributed as well.

The current version of qw works in 0.19 trunk and can start as any
species/background combination. Note though that spells and most racial
abilities aren't used, and qw is not very good at most combos! Its best
combo at the moment is DDFi^Makhleb, which managed a winrate of 14.5% in
offline testing. It is also quite good at some berserkers (9-10% winrate
with DDBe and GrBe) and has won MiFi^Ru.

## running on remote DCSS server
* go to e.g. http://crawl.akrasiac.org:8080/
* click "(edit rc)" link for DCSS trunk
* replace text that were here with contents of qw.rc file from this repo
* in ": DELAYED = false" and ": AUTO_START = false" lines change "false" to "true"
* you may also want to edit some of the configuration lines near the top
  of qw.rc (for instance to choose which combos qw will play)
* save and run DCSS trunk (either in webtiles or in console)
* enjoy!

Since clua works on the server side, webtiles drawing can lag behind things
actually happening, so the IRC bot [Sequell](https://github.com/greensnark/dcss_sequell) may tell you your character killed Sigmund or died to him before you see that with your own eyes. To see more current events just refresh the page and press "Tab". Alternatively, run or watch the bot in console (via ssh).

If you are familiar with Sequell, please add the name of the account that
you are using for qw to the "bot" nick with "!nick bot <accountname>" so
that games on the account can be easily filtered out of queries. (Also, please
don't run qw on the same account that you use for your own personal games!)

## running locally
* clone this repo
* run crawl locally with command like "./crawl -rc qw/qw.rc"
* enter name if necessary and start game. If you did not change "AUTO_START" variable, press "Tab"
* enjoy!

The file qw.exp is a simple expect script that automates running qw for many games in a row. The "AUTO_START" variable should be left at false when when using this. (With minor modifications, this can also be used to run games on a remote server over ssh.)

## miscellaneous tips for coding/testing qw
* run qw locally with the DCSS command-line option -seed <n> to use a seeded RNG for (mostly) reproducible testing
* uncomment the "say(plandata[2])" line in the cascade function to track what the bot is doing (very spammy)
* put code you want to test in the "ttt()" funtion on the bottom; make it run by macroing some key to "===ttt"
