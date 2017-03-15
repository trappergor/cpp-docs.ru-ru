---
title: "Использование CObject | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CObject - класс"
  - "производные классы, из CObject"
  - "примеры [MFC], CObject"
  - "MFC - библиотека, базовый класс"
  - "корневой базовый класс для MFC"
ms.assetid: d0cd19bb-2856-4b41-abbc-620fd64cb223
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Использование CObject
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CObject](../Topic/CObject%20Class.md) базовый класс для большинства корневой библиотеки Microsoft Foundation Class \(MFC\).  Класс `CObject` содержит много полезных функций, которые могут потребоваться для включения в собственные объекты программы, включая поддержку сериализации, данные класса среды выполнения и выходные данные диагностики объекта.  При наследовании от класса `CObject`, этот класс может воспользоваться эти функции `CObject`.  
  
## Выберите действие.  
  
-   [Унаследуйте класс от CObject](../mfc/deriving-a-class-from-cobject.md)  
  
-   [Добавить поддержку для данных класса среды выполнения, динамического создания и сериализации в производный класс my](../mfc/specifying-levels-of-functionality.md)  
  
-   [Доступ к данным класса среды выполнения](../mfc/accessing-run-time-class-information.md)  
  
-   [Создание объектов динамически](../Topic/Dynamic%20Object%20Creation.md)  
  
-   [Сбросьте данные объекта в целях диагностики для](http://msdn.microsoft.com/ru-ru/727855b1-5a83-44bd-9fe3-f1d535584b59)  
  
-   Проверьте внутреннее состояние объекта \(см. [ASSERT\_VALID MFC и CObject::AssertValid](http://msdn.microsoft.com/ru-ru/7654fb75-9e9a-499a-8165-0a96faf2d5e6)\)  
  
-   [Использовать класс сериализации в постоянное хранилище](../Topic/Serialization%20in%20MFC.md)  
  
-   Просмотрите список [Часто задаваемые вопросы CObject](../mfc/cobject-class-frequently-asked-questions.md)  
  
## См. также  
 [Основные понятия](../mfc/mfc-concepts.md)   
 [Общие разделы по MFC](../mfc/general-mfc-topics.md)   
 [CRuntimeClass Structure](../Topic/CRuntimeClass%20Structure.md)   
 [Файлы](../mfc/files-in-mfc.md)   
 [Сериализация](../Topic/Serialization%20in%20MFC.md)