Git is a distributed version control system.
Git is free software distributed under the GPL.
Git has a mutable index called stage.
Git tracks changes.
Creating a new branch is quick.
this line is fixed conflict dev and master

fix bug 101

git���
//��ʼ��
git init

//�ֿ⵱ǰ��״̬
git status

//����޸�����
git diff filename

//���ӻ��޸��ļ�
git add readme.txt
git commit -m "�޸ı�ע˵��"

//�鿴��ʷ��¼
git log
//�鿴��ʷ��¼--����
git log --pretty=oneline

//���˵�ĳһ�汾��HEAD��ʾ��ǰ�汾��HEAD^��һ�汾��HEAD~100��һ�ٸ��汾
git reset --hard HEAD^

//���ݰ汾ID���ˣ�����Ҫ����ȫ��ID��ֻ��Ҫǰ��λ�����־Ϳ���
git reset --hard 3628164

//��¼ÿһ������
git reflog

//�������������޸ģ�checkout���ð汾����İ汾�滻�������İ汾�����۹��������޸Ļ���ɾ���������ԡ�һ����ԭ����
git checkout -- filename

//���ݴ������޸ĳ�������unstage�������·Żع�������  ֮���ټ�����git checkout -- filename �������������޸ġ�
git reset HEAD file

//ɾ���汾���е��ļ�
git rm filename
git commit -m "remove filename"

//github ע�Ὠ���Ŀ�
https://github.com/610txc/learngit.git

//����һ��Զ�̿�
git remote add origin https://github.com/610txc/learngit.git
git remote add origin git@github.com:610txc/learngit.git

//��һ�ΰѱ��ؿ���������͵�Զ�� 
git push -u origin master

//�Ժ�ÿ�α��ؿ������ύ���Ϳ��԰ѱ���master��֧�������޸�������GitHub
git push origin master

//ɾ��Զ������
git remote remove origin

//��Զ�̿��¡һ�����ؿ⣬���ڱ��ص�ǰĿ¼�½���һ��gitskillsĿ¼
git clone https://github.com/610txc/gitskills.git

//����dev��֧��Ȼ���л���dev��֧
git checkout -b dev
//�൱��������������
git branch dev
git checkout dev

//�鿴��ǰ��֧
git branch

//�лص�master��֧
git checkout master

//��dev��֧�Ĺ����ɹ��ϲ���master��֧��
git merge dev

//ɾ��dev ��֧
git branch -d dev

�鿴��֧��git branch

������֧��git branch <name>

�л���֧��git checkout <name>

����+�л���֧��git checkout -b <name>

�ϲ�ĳ��֧����ǰ��֧��git merge <name>

ɾ����֧��git branch -d <name>

//��֧�ϲ���ͻʱ��Git��<<<<<<<��=======��>>>>>>>��ǳ���ͬ��֧�����ݣ������޸����º󱣴棬���ύ���� add ��commit

//�ô�������git logҲ���Կ�����֧�ĺϲ����
git log --graph --pretty=oneline --abbrev-commit

//��֧�ϲ�ʱ��git��Ĭ����Fast forwardģʽ��������ģʽ�£�ɾ����֧�󣬻ᶪ����֧��Ϣ
//���Ҫǿ�ƽ���Fast forwardģʽ��Git�ͻ���mergeʱ����һ���µ�commit���������ӷ�֧��ʷ�ϾͿ��Կ�����֧��Ϣ

//׼���ϲ�dev��֧����ע��--no-ff��������ʾ����Fast forward
git merge --no-ff -m "merge with no-ff" dev

//Git���ṩ��һ��stash���ܣ����԰ѵ�ǰ�����ֳ������ء����������Ժ�ָ��ֳ����������
git stash

//�鿴�����ء������ĵ�ǰ�����ֳ�
git stash list

//���ָֻ��취��
//һ�ǻָ���stash���ݲ���ɾ��
git stash apply
//һ�ǻָ���stash����ɾ��
git stash drop

//���Զ��stash���ָ���ʱ������git stash list�鿴��Ȼ��ָ�ָ����stash��������
git stash apply stash@{0}


https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/001376026233004c47f22a16d1f4fa289ce45f14bbc8f11000
//����һ����feature������½�һ����֧��
//���Ҫ����һ��û�б��ϲ����ķ�֧������ͨ��git branch -D <name>ǿ��ɾ��
git branch -D <branchname>

//�鿴Զ�̿����Ϣ��
git remote
//�鿴Զ�̿����ϸ��Ϣ������ץȡ�����͵ĵ�ַ
git remote -v

//������֧ʹ�ý��飺
master��֧������֧�����Ҫʱ����Զ��ͬ����
dev��֧�ǿ�����֧���Ŷ����г�Ա����Ҫ�����湤��������Ҳ��Ҫ��Զ��ͬ����
bug��ֻ֧�����ڱ����޸�bug����û��Ҫ�Ƶ�Զ���ˣ������ϰ�Ҫ������ÿ�ܵ����޸��˼���bug��
feature��֧�Ƿ��Ƶ�Զ�̣�ȡ�������Ƿ�����С�����������濪����

//���С���Ҫ��dev��֧�Ͽ������ͱ��봴��Զ��origin��dev��֧�����أ���������������������dev��֧��
git checkout -b dev origin/dev
//���Ϳ�����dev�ϼ����޸ģ�Ȼ��ʱ��ʱ�ذ�dev��֧push��Զ�̣�
git commit -m "add ������"
git push origin dev

//С����ύ����������devʧ�ܣ���Ϊ���С���������ύ������ͼ���͵��ύ�г�ͻ������취Ҳ�ܼ򵥣�
//Git�Ѿ���ʾ���ǣ�����git pull�����µ��ύ��origin/devץ������Ȼ���ڱ��غϲ��������ͻ��������
git pull

//���git pullҲʧ�ܣ�no tracking information���ˣ�ԭ����û��ָ������dev��֧��Զ��origin/dev��֧�����ӣ�������ʾ������dev��origin/dev�����ӣ�
git branch --set-upstream dev origin/dev

//git pull�ɹ������Ǻϲ��г�ͻ����Ҫ�ֶ����������ķ����ͷ�֧�����еĽ����ͻ��ȫһ����������ύ����push��

git commit -m "merge conflict with other person"
git push origin dev
