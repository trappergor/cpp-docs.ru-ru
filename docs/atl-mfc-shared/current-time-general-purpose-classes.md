---
title: 'Текущее время: Классы общего назначения | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- time, setting current
- current time, CTime object
- procedures, getting current time
- initializing objects, with the current time
- time, getting current
ms.assetid: c39e6775-6a92-4b27-95a7-5c86ed371d8a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ec71cf76f859457aa76e69b57b58db3940e974da
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="current-time-general-purpose-classes"></a>Текущее время: Классы общего назначения
Ниже показано, как создать `CTime` и инициализируйте его с текущим временем.  
  
#### <a name="to-get-the-current-time"></a>Чтобы получить текущее время  
  
1.  Выделить `CTime` объекта, как показано ниже:  
  
     [!code-cpp[NVC_ATLMFC_Utilities#171](../atl-mfc-shared/codesnippet/cpp/current-time-general-purpose-classes_1.cpp)]  
  
    > [!NOTE]
    >  Неинициализированный `CTime` объектов не инициализируются допустимое время.  
  
2.  Вызовите `CTime::GetCurrentTime` функции, чтобы получить текущее время из операционной системы. Эта функция возвращает `CTime` объекта, который может использоваться для задания значения `CTime`, как показано ниже:  
  
     [!code-cpp[NVC_ATLMFC_Utilities#172](../atl-mfc-shared/codesnippet/cpp/current-time-general-purpose-classes_2.cpp)]  
  
     Поскольку `GetCurrentTime` является статической функцией-членом из `CTime` класса, необходимо указать его имя с именем класса и оператора разрешения области действия (`::`), `CTime::GetCurrentTime()`.  
  
 Конечно два действия, описанные ранее можно объединить в одну инструкцию программы следующим образом:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#173](../atl-mfc-shared/codesnippet/cpp/current-time-general-purpose-classes_3.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Дата и время. Классы общего назначения](../atl-mfc-shared/date-and-time-general-purpose-classes.md)



