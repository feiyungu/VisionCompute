K-SVD
*******


����k-svd��ֱ��ʹ��ԭͼ��

K_SVD�㷨ģ��
=============

..math::

\min\limits{D,X}{||Y-DX||_F^2}\;  \;\;subject \;to \forall i, ||x_i||_0\leq T_0

�����K��over-complete�ֵ��С��

����dictionary D
=================
��ΪD��һ��������Ҫ���Ԫ�غܶ࣬�����������ÿ��ֻ����һ��D_j������$j\neq k$���䣬��������ķ�����

..math::

\begin{array}{l}
||Y-DX||_F^2=||Y-\sum_{j=1}^Kd_jx_T^j||_F^2\\
=||(Y-\sum_{j\neq k}d_jx_T^j)-d_kx_T^k||_F^2\\
=||E_k-d_kx_T^k||_F^2\\
\end{array}

��֤ʣ�������Ѿ����Ƶ���������

..math::

\begin{array}{l}
E_k^R=E_k\Omega,\\
x_R^k=x_T^k\Omega
\end{array}



�㷨�ܽ᣺
========

#.  ���ȹ���ϡ���ʾ��Ȼ������ֵ䣬���ֵ���Ƶ�ʱ�򣬲���ÿ��ֻ����һ��Dj���������䣬��������ķ�����
#.  ��k-means�ȽϽ��ƣ������ǲ�֪���κΣ�������D,����x��Ȼ����x�ֿ�ʼ����D��

�ο���
====

#. ǳ̸K-SVD http://www.cnblogs.com/salan668/p/3555871.html

