##### * In question 1, you named the intersection table user_question. What's a better name for that table?
Better table name be: questions_users

##### * In question 2, you said "If move from (a) to (b), ie single to multiple availability zone, then we have to set the Auto Scaling of load balancer". For what reason would using multiple availability zones require autoscaling? Unrelated question: you mention that data flows across the public internet in case (c)? How do you guarantee that data is in sync across multiple AWS regions?
Muiltple availability zones requires Autoscaling because:
- If one Availability Zone becomes unavailable or failed then Auto Scaling can launch another instances.
- It can help to handle large traffic on instances.
- It can dynamically increase and decrease capacity as needed which saves money.

-> There is a feature of AWS ie Cross Region Repliaction which replicates every object from one region to another and data is in sync state.

##### * In question 3, the question states that "there is a really dumb typo in one of your source code comments in commit A". I don't think your answer handles the case that was stated - it tries to fix a git commit comment, not a source code comment.
Steps to follow to change source code in commit and rewrite the history are:
- First run command: 
```sh
 git rebase --interactive 'SHA of A commit'
```
- In the editor, modify "pick" to "edit" in the line whose commit you want to modify. Make your changes and then commit them with the same message you had before. Then run command to modify the commit:
```sh
  git commit --all --amend --no-edit
```  
- Then run below command to return back to the previous head commit
```sh
 git rebase --continue
```
Note: Above commands will change the SHA-1 of that commit as well as all children.

##### * In question 5 you write,

```sh
  def comments
    self.comments
  end
```
##### Is it necessary to define the Post#comments instance method like this?
No, its not necessary, you can direct call "Post.find(post_id).comments" to fetch all comments for particular Post.

##### * In question 6, you seem to be searching for files whose name contains "aardvark". Please re-read the question.
Command: 
```sh
sudo grep -ir 'aardvark' /usr/local
```