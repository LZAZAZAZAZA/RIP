# RIP
Зубарева Елена, КН-202, n = 9

# Настройка
1) Создаем сеть в соответствии с указаниями в практике, на роутерах добавляем плату с разъемами для подключения дополнительных кабелей NM-1FE-TX. 
2) Через поле Config -> Interface устанавливаем соответствующие приведенным таблицам IP для интерфейсах на всем оборудовании. На PC0 и PC1 в качестве шлюза по умолчанию прописываем 10.9.1.2 (третий роутер)
3) Запускаем протокол RIP на каждом роутере:
*Router>en
Router#conf t
Router(config)#router rip
Router(config-router)#version 2
Router(config-router)#network <сеть>

# Результаты
Роутер 1

      Router>en
      Router#show ip route
      Codes: C - connected, S - static, I - IGRP, R - RIP, M - mobile, B - BGP
             D - EIGRP, EX - EIGRP external, O - OSPF, IA - OSPF inter area
             N1 - OSPF NSSA external type 1, N2 - OSPF NSSA external type 2
             E1 - OSPF external type 1, E2 - OSPF external type 2, E - EGP
             i - IS-IS, L1 - IS-IS level-1, L2 - IS-IS level-2, ia - IS-IS inter area
             * - candidate default, U - per-user static route, o - ODR
             P - periodic downloaded static route

      Gateway of last resort is not set

           10.0.0.0/24 is subnetted, 1 subnets
      C       10.9.1.0 is directly connected, FastEthernet0/1
      C    192.168.1.0/24 is directly connected, FastEthernet1/0
      R    192.168.2.0/24 [120/1] via 192.168.10.2, 00:00:23, FastEthernet0/0
      R    192.168.3.0/24 [120/1] via 10.9.1.2, 00:00:00, FastEthernet0/1
           192.168.10.0/24 is variably subnetted, 3 subnets, 2 masks
      R       192.168.10.0/24 [120/1] via 10.9.1.2, 00:00:00, FastEthernet0/1
      C       192.168.10.0/30 is directly connected, FastEthernet0/0
      R       192.168.10.4/30 [120/1] via 192.168.10.2, 00:00:23, FastEthernet0/0
