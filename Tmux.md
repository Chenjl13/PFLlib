# Run your training with Tmux!

### Update System
```
sudo apt update
```
### Tmux Installation
```
sudo apt install tmux
```
### Create a session
```
tmux new -s pflib
```
### Begin training
```
cd system
export LD_LIBRARY_PATH=/usr/lib/wsl/lib:$LD_LIBRARY_PATH
python main.py -data MNIST -m CNN -algo FedAvg -gr 20 -did 0
```
### Suspend
```
Ctrl + b
```
Release rapidly, Then press
```
 d
```
### Go back to see the status
```
tmux attach -t pflib
```
### Some useful command
View all Session
```
tmux ls
```
Get into Session
```
tmux attach -t pflib
```
Kill Session
```
tmux kill-session -t pflib
```














