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

.. math::

   \begin{array}{l}
   ||Y-DX||_F^2=||Y-\sum_{j=1}^Kd_jx_T^j||_F^2\\
   =||(Y-\sum_{j\neq k}d_jx_T^j)-d_kx_T^k||_F^2\\
   =||E_k-d_kx_T^k||_F^2\\
   \end{array}

��֤ʣ�������Ѿ����Ƶ���������

.. math::

   \begin{array}{l}
   E_k^R=E_k\Omega,\\
   x_R^k=x_T^k\Omega
   \end{array}



�㷨�ܽ�
========

#.  ���ȹ���ϡ���ʾ��Ȼ������ֵ䣬���ֵ���Ƶ�ʱ�򣬲���ÿ��ֻ����һ��Dj���������䣬��������ķ�����
#.  ��k-means�ȽϽ��ƣ������ǲ�֪���κΣ�������D,����x��Ȼ����x�ֿ�ʼ����D��

�ο�
====

#. ǳ̸K-SVD http://www.cnblogs.com/salan668/p/3555871.html

K-SVD: An Algorithm for Designing Overcomplete Dictionaries for Sparse Representation
=====================================================================================

���ֱ���Ϊextreme sparse represention��ÿ��ֻ�ܸ���һ��ԭ�ӡ�

..math:: D^{(n+1)}=D^{(n)}-\eta\sum_{i=1}^N(D^{(n)}x_i-y_i)x_i^T 

.. note::

   ���Ŀǰ����̫��⣬��x�ǹ����ġ�

.. code-block:: matlab

    noIt = 200
    [rows,cols]=size(y);
     r=randperm(cols); 
    A=y(:,r(1:codebook_size)); 
    A=A./repmat(sqrt(sum(A.^2,1)),rows,1); 
    D=A;
    X=y;
    K = 50;
    
    for it = 1:noIt
        W=OMP(D,X,4.0/5*rows); 
        R = X - D*W;  %���������Ӧ������  �������ģ�����Ӧ�ò�࣬���������ģ���һ��Ӧ�ð���Щ��
        for k=1:K
            I = find(W(k,:));
            Ri = R(:,I) + D(:,k)*W(k,I);  % ����һ�����������
            [U,S,V] = svds(Ri,1,'L');
            % U is normalized
            D(:,k) = U;
            W(k,I) = S*V';
            R(:,I) = Ri - D(:,k)*W(k,I);
        end    
    end

�������Եģ�Ȼ���������һ����D��W���໥�����ģ���˿��Թ��ơ�

ÿ��ֻ����һ�ԡ������Լ��Ҳ������D����W���ٱ仯
