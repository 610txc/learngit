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