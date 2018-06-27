---
title: Задание уровней функциональности | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CObject class [MFC], adding functionality to derived classes
- runtime [MFC], class information
- serialization [MFC], Cobject
- dynamic creation support
- levels [MFC], functionality in CObject
- run-time class [MFC], information support
- levels [MFC]
ms.assetid: 562669ba-c858-4f66-b5f1-b3beeea4f486
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 425cbf2f9c769dbbb6cd054b9af6b7f6f5fc9d52
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "36954469"
---
# <a name="specifying-levels-of-functionality"></a>Задание уровней функциональности
В этой статье описывается добавление следующих уровней функциональные возможности для вашего [CObject](../mfc/reference/cobject-class.md)-производного класса:  
  
-   [Сведения о классе во время выполнения](#_core_to_add_run.2d.time_class_information)  
  
-   [Поддержка динамического создания](#_core_to_add_dynamic_creation_support)  
  
-   [Поддержка сериализации](#_core_to_add_serialization_support)  
  
 Общее описание `CObject` функциональные возможности, см. в статье [наследование класса от CObject](../mfc/deriving-a-class-from-cobject.md).  
  
-   [Сведения о классе во время выполнения](#_core_to_add_run.2d.time_class_information)  
#### <a name="_core_to_add_run.2d.time_class_information"></a> Чтобы добавить сведения о классе во время выполнения  
  
1.  Создайте производный класс от `CObject`, как описано в [наследование класса от CObject](../mfc/deriving-a-class-from-cobject.md) статьи.  
  
2.  Используйте DECLARE_DYNAMIC-макрос в объявлении класса, как показано ниже:  
  
     [!code-cpp[NVC_MFCCObjectSample#2](../mfc/codesnippet/cpp/specifying-levels-of-functionality_1.h)]  
  
3.  Использовать IMPLEMENT_DYNAMIC-макрос в файле реализации (. CPP) этого класса. Этот макрос принимает в качестве аргументов имя класса и его базовых классов, как показано ниже:  
  
     [!code-cpp[NVC_MFCCObjectSample#3](../mfc/codesnippet/cpp/specifying-levels-of-functionality_2.cpp)]  
  
> [!NOTE]
>  Всегда помещать IMPLEMENT_DYNAMIC в файле реализации (. CPP) для своего класса. IMPLEMENT_DYNAMIC-макрос должен вычисляться только один раз во время компиляции и поэтому не следует использовать в файл интерфейса (. H), потенциально может включаться в более чем одного файла.  
  
#### <a name="_core_to_add_dynamic_creation_support"></a> Чтобы добавить поддержку динамического создания  
  
1.  Создайте производный класс от `CObject`.  
  
2.  DECLARE_DYNCREATE-макрос используйте в объявлении класса.  
  
3.  Определите конструктор без аргументов (конструктор по умолчанию).  
  
4.  Используйте implement_dyncreate-макрос в файле реализации класса.  
  
#### <a name="_core_to_add_serialization_support"></a> Для добавления поддержки сериализации  
  
1.  Создайте производный класс от `CObject`.  
  
2.  Переопределить `Serialize` функции-члена.  
  
    > [!NOTE]
    >  При вызове метода `Serialize` напрямую, то есть не требуется для сериализации объекта через указатель полиморфным, пропустите шаги с 3 по 5.  
  
3.  DECLARE_SERIAL-макрос используйте в объявлении класса.  
  
4.  Определите конструктор без аргументов (конструктор по умолчанию).  
  
5.  Используйте IMPLEMENT_SERIAL-макрос в файле реализации класса.  
  
> [!NOTE]
>  «Полиморфным указатель» указывает на объект класса (вызывать его A) или в объект класса, производного от параметр (скажем, B). Для сериализации через указатель полиморфного платформа необходимо определить класс среды выполнения объекта сериализуется (B), так как он может быть объект любого класса, производного от некоторого базового класса (A).  
  
 Дополнительные сведения о том, как включить сериализацию при получении класса из `CObject`, см. в статьях [файлы в MFC](../mfc/files-in-mfc.md) и [сериализации](../mfc/serialization-in-mfc.md).  
  
## <a name="see-also"></a>См. также  
 [Наследование класса от CObject](../mfc/deriving-a-class-from-cobject.md)
