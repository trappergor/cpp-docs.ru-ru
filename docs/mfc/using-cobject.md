---
title: Использование CObject | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CObject
dev_langs:
- C++
helpviewer_keywords:
- examples [MFC], CObject
- root base class for MFC
- derived classes [MFC], from CObject
- MFC, base class
- CObject class [MFC]
ms.assetid: d0cd19bb-2856-4b41-abbc-620fd64cb223
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 235bf1f4130f59a8af9548fcbf35e36d82255f14
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33382302"
---
# <a name="using-cobject"></a>Использование CObject
[CObject](../mfc/reference/cobject-class.md) является корневой базовый класс для большинства библиотеки классов Microsoft Foundation (MFC). `CObject` Класс содержит множество полезных возможностей, которые требуется включить в собственных объектов программы, включая поддержку сериализации, сведения о классе во время выполнения и диагностических выходных данных объекта. Если вы наследуете класс от `CObject`, класс может использовать эти `CObject` функции.  
  
## <a name="what-do-you-want-to-do"></a>Что Вы хотите делать  
  
-   [Создайте класс, производный от CObject](../mfc/deriving-a-class-from-cobject.md)  
  
-   [Добавить поддержку для сведения о классе во время выполнения, динамическое создание и сериализации для моей производного класса](../mfc/specifying-levels-of-functionality.md)  
  
-   [Сведения о классе во время выполнения доступ](../mfc/accessing-run-time-class-information.md)  
  
-   [Динамическое создание объектов](../mfc/dynamic-object-creation.md)  
  
-   [Дамп данных объекта в целях диагностики](http://msdn.microsoft.com/en-us/727855b1-5a83-44bd-9fe3-f1d535584b59)  
  
-   Проверка внутреннего состояния объекта (в разделе [MFC ASSERT_VALID и CObject::AssertValid](http://msdn.microsoft.com/en-us/7654fb75-9e9a-499a-8165-0a96faf2d5e6))  
  
-   [Сделайте класс сериализоваться в постоянное хранилище](../mfc/serialization-in-mfc.md)  
  
-   Просмотреть список [CObject вопросы и ответы](../mfc/cobject-class-frequently-asked-questions.md)  
  
## <a name="see-also"></a>См. также  
 [Основные понятия](../mfc/mfc-concepts.md)   
 [Общие разделы по MFC](../mfc/general-mfc-topics.md)   
 [Структура CRuntimeClass](../mfc/reference/cruntimeclass-structure.md)   
 [Файлы](../mfc/files-in-mfc.md)   
 [Сериализация](../mfc/serialization-in-mfc.md)

