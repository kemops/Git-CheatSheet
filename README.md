#### กระบวนการ Git ฉบับเต็ม (4 โซน):
1.`Working Directory`: โฟลเดอร์ในเครื่องที่คุณกำลังแก้ไฟล์   
2.`Staging Area (Index)`: พื้นที่เตรียมตัว (ใช้คำสั่ง git add เพื่อเอาไฟล์มาพักไว้)   
3.`Local Repository`: ประวัติที่บันทึกลงเครื่องอย่างถาวร (ใช้คำสั่ง git commit เพื่อยืนยัน)   
4.`Remote Repository`: ที่เก็บโค้ดบนเซิร์ฟเวอร์/คลาวด์ เช่น GitHub, GitLab (ใช้คำสั่ง git push ส่งขึ้นไป และ git pull ดึงลงมา)   

### สถานะไฟล์ใน Git มี 4 ระยะ (Lifecycle) ครับ:
1.`Untracked` (ยังไม่รู้จัก): ไฟล์เพิ่งสร้างใหม่ Git ยังไม่เคยจำ (รอใช้ git add)   
2.`Unmodified` (ปกติ): ไฟล์ที่เคยบันทึกแล้ว และยังไม่ได้แก้ไขอะไรเพิ่ม   
3.`Modified` (แก้แล้ว): ไฟล์เก่าที่เพิ่งถูกแก้ไขเนื้อหา (ต้องใช้ git add อีกรอบเพื่ออัปเดต)  
4.`Staged` (เตรียมพร้อม): ไฟล์ที่ผ่านการ git add เข้าไปรอใน Staging Area แล้ว (รอ git commit)   

### GIT-CLI
```
git config --global user.email <"email ex: user@gmail.com">
git config --global user.name "kemops"
git config --list

git init
git status
git add . | git add *.ps1
git rm --cached app.js                                       // ใช้กรณี เคยcommit ไปแล้วแล้วจะเอาเข้า .ignore
git restore --staged app.js | git reset app.js               // เหมือนกัน เอาออกจาก Staging Area
git log --oneline | --graph  
git diff <commit_id> <commit_id>

git checkout app.js                       // เหมือนการกด Undo app.js
git show HEAD | git show <commit_id>
git reset --option <commit_id> | --soft,--mixed,--hard
git branch                                // เช็ค Branch
git branch -d <name_branch>               // ลบ Branch
git checkout <name_branch>                // สลับ Branch
git checkout -b <name_branch>             // สร้างและสลับ Branch
git merge <name_branch>                   // รวม Branch

git branch -m main
git remote add origin https://github.com/kemops/git-cheatsheet.git
git push -u origin main
git pull
git clone https://github.com/kemops/git-cheatsheet.git       //ครั้งแรก

```
### GITHUB-CLI
```
winget install --id GitHub.cli
gh auth login
gh repo create <name_repo> --private --source=. --remote=origin --push
gh repo edit --visibility public --accept-visibility-change-consequences
gh repo view kemops/git-cheatsheet
gh repo list kemops  |  gh repo list docker --limit 10

gh auth refresh -h github.com -s delete_repo
gh repo delete hello-git --yes
```
