# qw
This rcfile is elliptic's DCSS bot "qw", the first (and thus far only) bot
to win DCSS with no human assistance. A substantial amount of code here was
contributed by elliott or borrowed from N78291's bot "xw".

The current version of qw works in 0.16 trunk and can play berserkers of
any species. In offline testing, it has a winrate of over 5% with GrBe (and
also very respectable winrates with DDBe and MiBe).

Most racial abilities aren't used: Fo shafting/digging, Dr breath, Na spit,
Sp running away, Gh eating to heal, etc.
With minor modifications, qw will play non-Be and convert to Trog; it has
won DDSu offline this way.

## running on remote DCSS server
* go to e.g. http://crawl.s-z.org/
* click "(edit rc)" link for DCSS trunk
* replace text that were here with contents of qw.rc file from this repo
* in `: DELAYED = false` and `: AUTO_START = false` lines change `false` to `true`
* you may also want to edit lines setting `combo` variable
* save and run DCSS trunk
* enjoy!

Since clua works on the server side, drawing can lag behind things actually 
happening, and [Sequell](https://github.com/greensnark/dcss_sequell) can tell you your
character killed Sigmund or died to him before you see that with your own eyes.

To see more current events just refresh page and press `Tab`.

## running locally
* clone this repo
* run crawl locally with command like `./crawl -rc qw/qw.rc`
* enter name if necessary and start game. If you did not change `AUTO_START` variable, press `Tab`
* enjoy!

## hacking
* put the code you want to test in the `ttt()` funtion on the bottom
* make it run when you want, e.g. by redefining `hit_closest()` function to call `ttt()` instead
* press `Tab` to run your code
