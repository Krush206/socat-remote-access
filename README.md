# Socat Remote Access
A password-based Shell script that provides similar functionality of SSH servers, but in a simpler way.

I made this script so that I could remote access machines with more ease, as well as machines that do not have a SSH server installed.

#### How to use
Install [socat](http://www.dest-unreach.org/socat), change the script's execution permissions and run the following:\
``( export master_pw="`head -1`" ; socat -v exec:"nc -kl 0.0.0.0 <port>",crnl exec:./socat-remote,stderr )``

#### Notes
For multiple remote accesses, replace `exec:"nc -kl 0.0.0.0 <port>",crnl` with `tcp-l:<port>,fork,reuseaddr,crnl`

The script is compatible with Windows (Cygwin).

Encryption can be achieved using a P2P VPN software. (Recommend [n2n](https://meshvpn.blogspot.com/2020/12/n2n-ntop.html).)

Environment variables are preserved for each program or command the Shell executes, therefore I don't recommend to run the script without a sub-shell.
