---
title: "Практическое руководство. Создание виртуальной схемы сообщений для класса шаблона | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "схемы сообщений, классы шаблонов"
  - "классы шаблонов, создание схем сообщений"
ms.assetid: 4e7e24f8-06df-4b46-82aa-7435c8650de3
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Практическое руководство. Создание виртуальной схемы сообщений для класса шаблона
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Сопоставление сообщения в MFC предоставляет эффективный способ непосредственно Windows сообщения в соответствующий экземпляр объекта C C\+\+.  Примеры целевых объектов схемы сообщений относятся классы MFC приложения, классы документов и представлений, классы элементов управления и т д  
  
 Объявлены, используя макрос [BEGIN\_MESSAGE\_MAP](../Topic/BEGIN_MESSAGE_MAP.md) объявлен, что традиционные сопоставления сообщений MFC начала сопоставления сообщений, запись макроса для каждого метода класса обработчика сообщений и, наконец макрос [END\_MESSAGE\_MAP](../Topic/END_MESSAGE_MAP.md) объявлен конца сопоставления сообщений.  
  
 Одно ограничение с макросом [BEGIN\_MESSAGE\_MAP](../Topic/BEGIN_MESSAGE_MAP.md) выполняется, когда он используется совместно с классом, содержащая аргументы шаблона.  При использовании с шаблонным классом, этот макрос приведет к ошибке времени компиляции ошибку с отсутствующими параметрам шаблона при выполнении расширения макроса.  Макрос [BEGIN\_TEMPLATE\_MESSAGE\_MAP](../Topic/BEGIN_TEMPLATE_MESSAGE_MAP.md) был разработан для разрешения классы, содержащий один аргумент шаблона для объявления собственные схемы сообщений.  
  
## Пример  
 Рассмотрим пример, в котором класс MFC [CListBox](../Topic/CListBox%20Class.md) расширяется, чтобы обеспечить синхронизацию с внешним источником данных.  Вымышленный класс **CSyncListBox** объявляется следующим образом:  
  
 [!code-cpp[NVC_MFC_CListBox#42](../mfc/codesnippet/CPP/how-to-create-a-message-map-for-a-template-class_1.h)]  
  
 Класс **CSyncListBox** атрибутами в одном типе, который описывает источник данных его синхронизировать с.  Он также объявить 3 метода, которые будут участвовать в схеме классов сообщений: **OnPaint**, **OnDestroy** и **OnSynchronize**.  Метод **OnSynchronize** реализуется следующим образом:  
  
 [!code-cpp[NVC_MFC_CListBox#43](../mfc/codesnippet/CPP/how-to-create-a-message-map-for-a-template-class_2.cpp)]  
  
 Описанная выше реализация позволяет класс **CSyncListBox**, чтобы настроить на любом типе класса, который реализует метод **GetCount**, например **CArray**, **CList** и **CMap**.  Функция **StringizeElement** шаблонная функция с прототипом:  
  
 [!code-cpp[NVC_MFC_CListBox#44](../mfc/codesnippet/CPP/how-to-create-a-message-map-for-a-template-class_3.cpp)]  
  
 Обычно схема сообщений для этого класса может быть определена следующим образом:  
  
 `BEGIN_MESSAGE_MAP(CSyncListBox, CListBox)`  
  
 `ON_WM_PAINT()`  
  
 `ON_WM_DESTROY()`  
  
 `ON_MESSAGE(LBN_SYNCHRONIZE, OnSynchronize)`  
  
 `END_MESSAGE_MAP()`  
  
 пользователя **LBN\_SYNCHRONIZE**, где пользовательское сообщение, определенное приложением, например:  
  
 [!code-cpp[NVC_MFC_CListBox#45](../mfc/codesnippet/CPP/how-to-create-a-message-map-for-a-template-class_4.cpp)]  
  
 Сопоставление вышеуказанное макроса не будет компилироваться, из\-за факту, спецификация шаблона класса **CSyncListBox** будет потерян при выполнении расширения макроса.  Макрос **BEGIN\_TEMPLATE\_MESSAGE\_MAP** это решает, включив указанный параметр шаблона в развернутое сопоставление макроса.  Схема сообщений для этого класса становится:  
  
 [!code-cpp[NVC_MFC_CListBox#46](../mfc/codesnippet/CPP/how-to-create-a-message-map-for-a-template-class_5.cpp)]  
  
 В следующем примере демонстрируется потребление примера класса **CSyncListBox** с помощью объекта **CStringList**:  
  
 [!code-cpp[NVC_MFC_CListBox#47](../mfc/codesnippet/CPP/how-to-create-a-message-map-for-a-template-class_6.cpp)]  
  
 Для выполнения теста функция **StringizeElement** должен быть настроен для работы с классом **CStringList**:  
  
 [!code-cpp[NVC_MFC_CListBox#48](../mfc/codesnippet/CPP/how-to-create-a-message-map-for-a-template-class_7.cpp)]  
  
## См. также  
 [BEGIN\_TEMPLATE\_MESSAGE\_MAP](../Topic/BEGIN_TEMPLATE_MESSAGE_MAP.md)   
 [Обработка и сопоставление сообщений](../mfc/message-handling-and-mapping.md)