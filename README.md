# hse_hw1_meth
https://colab.research.google.com/drive/1VmhoR_adAh7fbn5lenFYZGGqERjouR8k?usp=sharing

# 1. Aнализ QC прочтений 
Наблюдается значительное преобладание GC нуклеотидов в сравнении с остальными (per sequence GC content). Учитывая то, что для qc отчета нами был выбра образец, для которого, по нашим предположениям, увеличивается уровень метилирования, наблюдаемая картина подтверждает наши предположения.

# 2. Работа с bam-files с выравниваниями BS-seq ридов на 11-ю хромосому мыши (используем samtools view) :

![image](https://user-images.githubusercontent.com/93148620/154337759-11b6b00e-b079-443d-977d-81ba50b2b7db.png)

(Это таблица с числом ридов, закартированных на участки 11347700-11367700; 40185800-40195800)

# 3. Дедупликация файлов выравниваний. Сколько процентов прочтений дуплицированно в каждом из образцов:

![image](https://user-images.githubusercontent.com/93148620/154338373-1c1e6600-ea22-48da-8217-9eee32045418.png)

* bash-скрипт для выполнения дедупликации для всех образцов одновременно см в google colab

# 4. Проведён коллинг метилирования цитозинов.

# 5. Выведите отчет в формате html. Файл html загрузите в директорию github. Прикрепите скриншот M-bias plot и кратко опишите, что вы на нем видите
Описание: из документации сладует, что графики показывают долю метелированиях на всех позициях хромосомы. Можно пронаблюдать, что больше всего метилирования происходит в образце Epiblast, значительно меньше в 8Cell, и совсем мало в ICM.

# SRR5836473 (8Cell):
<img width="813" alt="image" src="https://user-images.githubusercontent.com/93148620/154362489-570a6638-236f-4149-97a2-a1eb1f921352.png">
<img width="805" alt="image" src="https://user-images.githubusercontent.com/93148620/154362564-7f7ce20d-523f-4a6e-afd7-5c0b147ef25a.png">

# SRR3824222 (Epiblast):
<img width="827" alt="image" src="https://user-images.githubusercontent.com/93148620/154362836-bd88e7f8-79c6-4df0-9f06-a4c8a5e5f5dc.png">
<img width="811" alt="image" src="https://user-images.githubusercontent.com/93148620/154362890-f94e1d65-04e6-4759-979e-be59adaaf9ca.png">

# SRR5836475 (ICM):
<img width="892" alt="image" src="https://user-images.githubusercontent.com/93148620/154362938-6a9368eb-f095-49b8-aebc-407517d50245.png">
<img width="892" alt="image" src="https://user-images.githubusercontent.com/93148620/154362982-ca254c34-308d-4ca0-8773-b2039df20a79.png">


# 6. С помощью файла bismark.cov или .bedgraph постройте гистограмму распределения метилирования цитозинов по хромосоме (отображение насколько часто метилируются цитозины в данном образце: по X процент метилированных цитозинов, по Y - частота). Сделайте выводы. Код построения гистограммы нужно прикрепить.

![image](https://user-images.githubusercontent.com/93148620/154338895-ab30264a-4383-4486-b604-0a09923157d2.png)

![image](https://user-images.githubusercontent.com/93148620/154338928-f6583501-f442-4544-bd04-2c7e48b5ecc5.png)

![image](https://user-images.githubusercontent.com/93148620/154338952-e8d89471-1527-4b07-9e03-95b19b1bfcb0.png)

Вывод: для образца Epiblast мы наблюдаем максимальный уровень метилирования днк, в этом случае метилируется большая часть хромосомы. В образце ICM метилирования практически не происходит, а в 8Cell - имеет место быть, но не так значительно, как в Epiblast. Т.е. мы видим, что на разных этапах развития эмбриона, уровень метилирования действительно меняется.

Код:
<img width="552" alt="image" src="https://user-images.githubusercontent.com/93148620/154362116-0909a031-885d-4a4c-b546-79a7f5038c45.png">


# 7. Визуализируйте уровень метилирования и покрытия для каждого образца (для этого нужно составить файл с трэками, читайте мануал). С помощью pyGenomeTracks. 

Уровень метилирования:
![image_meth](https://user-images.githubusercontent.com/93148620/154361859-df0522bd-4af9-4536-a6f9-f72f3031f021.png)

Уровень покрытия:
![image_cov (1)](https://user-images.githubusercontent.com/93148620/154361907-8d88cd39-9ac6-44d7-89ea-bb8002cf2929.png)



