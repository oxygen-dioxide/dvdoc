# ��������
���ڣ���������Ĺ������Ѿ���ɣ�����dv��ʹ��ֻ�����һ��������������

dvtb����Ƶ��ԭ���趨����Ϊ��׺��ΪDVModel���м��ļ����ٴ��Ϊdv��Դ������SKC��SKI��voice.sksd�����ļ�������������javaԴ�ļ�����Ϊclass�ļ����ٴ��Ϊjar����

## ����
��dvtb��Function->Build Voice Bank�����������������

![](Resource/2020-09-07-10-29-38.png)

1. �ڡ�wav location���У�����Դ�����е���Ƶ�ļ�����ӽ�����
2. ��Model symbol�У�ѡ�����ȫ����������һ������߱���ָ���������ڶ������������ı�������������Ҫ����ķ�����
3. �����Model File Location����ѡ������DVModel�ļ����ļ���
4. �����Ҫ�������е�DVModel�ļ�����ѡ�С�Overwrite existing models��
5. �����Build Voice Model File����ѡ����־�ļ��Ĵ��λ�ã���ʼ���롣

��������ʱ����������ö��죬����CVVCÿ�����״�Լ��Сʱ��

��������У������ԭ���趨�͹��͵����ʻᵼ�±�����������ʱ������Ӧ���ԭ���趨�Ƿ��д����ٰ����±��Ų顣�����Ǳ�����Ϣ�ĺ��壺

|������Ϣ|����|����ԭ����������|
|-|-|-|
|File create failed | �ļ�����ʧ�� | �ļ���ռ�û���Ȩ�ޣ��뽫DVModel�ļ��Ĵ��λ�������ڷ�ϵͳ�� |
|Markers sequence error | ���˳����� | һ��������dvcfg�ļ��ĵ����������bug |
|Unvoiced part exists in voiced consonant | �Ǹ����г���������| �볢�Խ���������ĸ����Ƶ��帨���б��У������±��� |
|Unvoiced part exists in vowel | Ԫ���г��������� | ��Ƶ��������������ͬƴ���滻����¼ |
|Unvoiced part exists in the start of this continuant | ����������ʼ�������� | ��Ƶ��������������ͬƴ���滻����¼ |
|Symbol error | ���Ŵ��󣬲����Ϲ淶 | |
|Pitch symbol error | ���߷��Ŵ��� | |
|Unvoiced part exists in continuant to vowel | V_V�г���������| Ԫ�����Ӵ�Ҫ��������Ҫ�Ͽ� |
|Unvoiced part exists in continuant to voiced consonant | V_C(�Ǹ���)�г���������| �볢�Խ���������ĸ����Ƶ��帨���б��У������±��� |

## ���
�����ڱ�����������

6. ��Pitch Symbol��������������Ҫ���������
7. ��Singer Name��������Դ����
8. ѡ�񵼳���Դ���ļ���
9. �����Build Voice Bank����ѡ����־�ļ��Ĵ��λ�ã���ʼ���

�������ʱ��һ����1�����ڣ���������ļ���������SKC��SKI��voice.sksd�����ļ��������ɺ����ʾȱʧ��DVModel�м��ļ���