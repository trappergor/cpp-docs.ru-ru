---
title: "Предупреждение средств компоновщика LNK4092 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4092
dev_langs:
- C++
helpviewer_keywords:
- LNK4092
ms.assetid: d569ec47-a338-40e1-940b-8a8061459acb
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 64d4e7a96009f8b3f2de1ee83f143427542ded65
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-warning-lnk4092"></a>Предупреждение средств компоновщика LNK4092
Общий доступный для записи раздел «раздел» содержит перемещенные элементы; образ может выполняться некорректно  
  
 Компоновщик выдает это сообщение каждый раз, когда используете общий раздел, чтобы предупредить о потенциальных проблемах.  
  
 Один способ обмена данными между несколькими процессами — отметить раздел как «общий». Однако создание раздела как общего может вызвать проблемы. Например у вас есть библиотеку DLL, которая содержит объявления в общем разделе данных:  
  
```  
int var = 1;  
int *pvar = &var;  
```  
  
 Компоновщик не может разрешить `pvar` , поскольку его значение зависит от того, когда библиотека DLL загружается в память, поэтому помещает запись о перемещении в библиотеку DLL. Если библиотека DLL загружается в память, адрес `var` можно разрешить и `pvar` назначен. Если другой процесс загружает ту же библиотеку DLL, но не может загрузить ее в то же адрес, перемещение адреса `var` будет обновлено для второго процесса и пространство адресов первого процесса будет указывать на неверное местоположение.
