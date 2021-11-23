## tmux 

Start : tmux 

Horizontal banes within windows : Ctl + b,  %
Vertical banes within windows : Ctrl + b, "
Switching bw banes : Ctrl + b, [arrow keys]

Rename banes : Ctrl + b, ,
Rename session: tmux rename-session -t [SESSION_OLD_NAME] [SESSION_NEW_NAME]

List of tmux sessions : tmux ls

Attach sessions: tmux attach -t 0 [tmux attach -(target session) name_of_the_session ]
Detach a session: Ctrl + b, d
New session: tmux new -s [NAME_OF_SESSION]
Kill session: tmux kill-session -t [NAME_OF_TARGET_SESSION]

Close : exit

# wmctrl
window manager control. 
check which window manager is running :     wmctrl -m 
