�׾����㷨
**************


Nystrom method
===============

�����ݼ�֮������ƶȾ��󣬹�������ƶ�ͼ��Ȼ�����ĳ����ʽ��Laplacian Matrix,Ȼ�����Laplacian matrix��ǰk���������������k������������ɵľ���U��ǰK����������Ϊ���룬����K-means �㷨���õ����ľ���������Ҫ����������������д����ںܶ�Ӧ���ǲ����ϵġ������ڵ����ݹ�ģ�޴�ʱ�����׾����㷨�ĳ�����

Nystrom Method �������������ʽ�Ļ��ַ��̣�

.. math::
   \int_a^b W(x,y)\phi(y)dy = \lambda \phi(x)

��[a,b]�м�ȡn�����ֵ㣬���þ���ʽ������д����ֵ������ʽ��

.. math::

   \frac{b-a}{n}\sum_{j=1}^n W(\xi_i,\xi_j)\hat\phi(\xi_j) =\lambda(\hat\phi\xi_i) \existsi \in {1,...,n}

����أ���[a,b]Ϊ[0,1], ��ʽ��ʾ�ɾ�����ʽ�� :math:`A\hat\Phi`=n\hat\Phi`\Lambda. ���ǵõ� Nystrom Extension��ʽ��

.. math::

   \hat\Phi_i(x)= \frac{1}{n\lambda}\sum_{j=1}^nW(x,\xi_j)\hat\phi_i(\xi_j)


 �����ʽ��������ֽ���Ա�ʾ�ɾ���ֽ���ʽ��

http://blog.sciencenet.cn/blog-799581-626691.html
