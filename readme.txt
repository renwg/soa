http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000


GitHub�û���Ϣ renwg rwg123456

1��windowsƽ̨���ص�ַ
   http://msysgit.github.io/

2����װ��ɺ󣬻���Ҫ���һ�����ã������������룺
   $ git config --global user.name "trumol"
   $ git config --global user.email "475609041@qq.com"

   //��ΪGit�Ƿֲ�ʽ�汾����ϵͳ�����ԣ�ÿ�������������Ա����ţ�������ֺ�Email��ַ��
   //git config�����--global���������������������ʾ����̨���������е�Git�ֿⶼ��ʹ��������ã�

3�������汾��
   3.1 ��һ����ѡ��һ�����ʵĵط�������һ����Ŀ¼��
   $ mkdir E:/repository
   $ cd E:/repository
   $ pwd
    E/repository

   3.2 �ڶ�����ͨ��git init��������Ŀ¼���Git���Թ���Ĳֿ⣺
   $ git init

4����һ���ļ��ŵ�Git�ֿ�ֻ��Ҫ������
   4.1 ��һ����������git add����Git�����ļ���ӵ��ֿ⣺
   $ git add readme.txt

   4.2 �ڶ�����������git commit����Git�����ļ��ύ���ֿ⣺
   $ git commit -m "wrote a readme file"

5������git status��������

6���鿴��ʷ��¼
   ��Git�У�������git log����鿴��
   $ git log --pretty=oneline

7���汾����
   ����Ҫ�ѵ�ǰ�汾��append GPL�����˵���һ���汾��add distributed�����Ϳ���ʹ��git reset���
   ��Git�У���HEAD��ʾ��ǰ�汾,
   ��һ���汾����HEAD^������һ���汾����HEAD^^����Ȼ����100���汾д100��^�Ƚ�������������������д��HEAD~100
   $ git reset --hard HEAD^

8���ָ���ָ���汾 git reset --hard commit_id
   $ git reset --hard cb926e7

9����git reflog�鿴������ʷ���Ա�ȷ��Ҫ�ص�δ�����ĸ��汾��
   $ git reflog

10����git log���Բ鿴�ύ��ʷ���Ա�ȷ��Ҫ���˵��ĸ��汾��
   $ git log --pretty=oneline

11�������޸� git checkout -- file
   $ git checkout -- readme.txt

12��ɾ��������git rm����ɾ��һ���ļ�
   $ git rm readme.txt

13��Զ�ֿ̲�
   ��1��������SSH Key�����û���Ŀ¼�£�������û��.sshĿ¼������У��ٿ������Ŀ¼����û��id_rsa��id_rsa.pub�������ļ�������Ѿ����ˣ���ֱ��������һ�������û�У���Shell��Windows�´�Git Bash��������SSH Key��
   $ ssh-keygen -t rsa -C "475609041@qq.com"
   ����س���OK�����һ��˳���Ļ����������û���Ŀ¼���ҵ�.sshĿ¼��������id_rsa��id_rsa.pub�����ļ�������������SSH Key����Կ�ԣ�id_rsa��˽Կ������й¶��ȥ��id_rsa.pub�ǹ�Կ�����Է��ĵظ����κ��ˡ�

   ��2������½GitHub���򿪡�Account settings������SSH Keys��ҳ�棺
   Ȼ�󣬵㡰Add SSH Key������������Title����Key�ı�����ճ��id_rsa.pub�ļ������ݡ�

   ΪʲôGitHub��ҪSSH Key�أ���ΪGitHub��Ҫʶ��������͵��ύȷʵ�������͵ģ������Ǳ���ð��ģ���Git֧��SSHЭ�飬���ԣ�GitHubֻҪ֪������Ĺ�Կ���Ϳ���ȷ��ֻ�����Լ��������͡�
	��Ȼ��GitHub��������Ӷ��Key���ٶ��������ɵ��ԣ���һ����ڹ�˾�ύ��һ����ڼ����ύ��ֻҪ��ÿ̨���Ե�Key����ӵ�GitHub���Ϳ�����ÿ̨��������GitHub�����ˡ�
	���������ʾ����GitHub������йܵ�Git�ֿ⣬�κ��˶����Կ���ร���ֻ�����Լ����ܸģ������ԣ���Ҫ��������Ϣ�Ž�ȥ��
	����㲻���ñ��˿���Git�⣬�������취��һ���ǽ��㱣���ѣ���GitHub�ѹ����Ĳֿ���˽�еģ��������˾Ϳ������ˣ����ɶ�������д������һ���취���Լ����֣���һ��Git����������Ϊ�����Լ���Git�����������Ա���Ҳ�ǿ������ġ�����������Ǻ���ὲ���ģ��൱�򵥣���˾�ڲ������ر���
	ȷ����ӵ��һ��GitHub�˺ź����Ǿͼ�����ʼԶ�ֿ̲��ѧϰ��

14�����Զ�ֿ̲�
    Ҫ����һ��Զ�̿⣬ʹ������
    git remote add origin git@server-name:path/repo-name.git��

    ������ʹ������,��һ������master��֧����������
    git push -u origin master

    �˺�ÿ�α����ύ��ֻҪ�б�Ҫ���Ϳ���ʹ���������������޸ģ�
    git push origin master

    ���Ѿ��ڱ��ش�����һ��Git�ֿ��������GitHub����һ��Git�ֿ⣬�������������ֿ����Զ��ͬ����������GitHub�ϵĲֿ�ȿ�����Ϊ���ݣ��ֿ�����������ͨ���òֿ���Э��������һ�ٶ�á�
    ��һ������½GitHub��Ȼ�������Ͻ��ҵ���Create a new repo����ť������һ���µĲֿ⣺
    ��Repository name����trumol����������Ĭ�����ã������Create repository����ť���ͳɹ��ش�����һ���µ�Git�ֿ⣺
    Ŀǰ����GitHub�ϵ����trumol�ֿ⻹�ǿյģ�GitHub�������ǣ����Դ�����ֿ��¡���µĲֿ⣬Ҳ���԰�һ�����еı��زֿ���֮������Ȼ�󣬰ѱ��زֿ���������͵�GitHub�ֿ⡣

    ���ڣ����Ǹ���GitHub����ʾ���ڱ��ص�learngit�ֿ����������
    $ git remote add origin git@github.com:renwg/trumol.git

    ��ǧ��ע�⣬�������michaelliao�滻�����Լ���GitHub�˻������������ڱ��ع����ľ����ҵ�Զ�̿⣬����û�����⣬�������Ժ��������Ʋ���ȥ�ģ���Ϊ���SSH Key��Կ�����ҵ��˻��б��С�
    ��Ӻ�Զ�̿�����־���origin������GitĬ�ϵĽз���Ҳ���Ըĳɱ�ģ�����origin�������һ����֪����Զ�̿⡣

    �ڶ������ѱ��ؿ�������������͵�Զ�̿��ϣ�
    $ git push -u origin master

15����Զ�̿��¡
    ʹ��git clone�����¡�����磺https://github.com/twbs/bootstrap
    $ git clone git@github.com:twbs/bootstrap.git

16��������ϲ���֧

     �鿴��֧��git branch
     ������֧��git branch <name>
     �л���֧��git checkout <name>
     ����+�л���֧��git checkout -b <name>
     �ϲ�ĳ��֧����ǰ��֧��git merge <name>
     ɾ����֧��git branch -d <name>

     ��һ�������Ǵ���dev��֧��Ȼ���л���dev��֧(-b������ʾ�������л�)��
     $ git checkout -b dev

     �ڶ�����
     $ git add readme.txt 
     $ git commit -m "branch test"

     ���������л���master��֧
     $ git checkout master

     �л���master��֧���ٲ鿴һ��readme.txt�ļ����ղ���ӵ����ݲ����ˣ���Ϊ�Ǹ��ύ����dev��֧�ϣ���master��֧�˿̵��ύ�㲢û�б䡣

     ���Ĳ�����dev��֧�Ĺ����ɹ��ϲ���master��֧��
     $ git merge dev

     ���岽���ϲ���ɺ󣬾Ϳ��Է��ĵ�ɾ��dev��֧��
     $ git branch -d dev

17������Э��
     ����Э���Ĺ���ģʽͨ����������

     ��һ��,�ȸ���:
     $ git pull

     �ڶ���,�ύ:
     $ git push origin branch-name

     ע�⣺
     ���git pull��ʾ��no tracking information������˵�����ط�֧��Զ�̷�֧�����ӹ�ϵû�д�����������
     $ git branch --set-upstream branch-name origin/branch-name

     �鿴Զ�̿���Ϣ��ʹ��
     $ git remote -v

     �ڱ��ش�����Զ�̷�֧��Ӧ�ķ�֧��ʹ��
     $ git checkout -b branch-name origin/branch-name


https://github.com/twbs/bootstrap
http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/001375840202368c74be33fbd884e71b570f2cc3c0d1dcf000
  
