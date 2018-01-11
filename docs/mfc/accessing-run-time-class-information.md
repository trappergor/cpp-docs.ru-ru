---
title: "Доступ к сведениям о классе во время выполнения | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CObject class [MFC], and RTTI
- CObject class [MFC], using IsKindOf method [MFC]
- run time [MFC], class information
- RUNTIME_CLASS macro [MFC]
- CObject class [MFC], using RUNTIME_CLASS macro [MFC]
- RTTI compiler option [MFC]
- CObject class [MFC], accessing run-time class information
- run time [MFC]
- IsKindOf method method [MFC]
- run-time class [MFC], accessing information
- classes [MFC], run-time class information
- run-time class [MFC]
- RUNTIME_CLASS macro, using
ms.assetid: 3445a9af-0bd6-4496-95c3-aa59b964570b
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0b74c76e5cc156d106f8358fe729df0bb7026422
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="accessing-run-time-class-information"></a>Доступ к сведениям о классе во время выполнения
В этой статье объясняется, как получать доступ к сведениям о классе объекта во время выполнения.  
  
> [!NOTE]
>  Не использует MFC [информацию о типах времени выполнения](../cpp/run-time-type-information.md) (RTTI) поддержка которых появилась в Visual C++ 4.0.  
  
 Если производного класса из [CObject](../mfc/reference/cobject-class.md) и использовать **DECLARE**_**динамическое** и `IMPLEMENT_DYNAMIC`, `DECLARE_DYNCREATE` и `IMPLEMENT_DYNCREATE`, или `DECLARE_SERIAL` и `IMPLEMENT_SERIAL` макросы описано в статье [наследование класса от CObject](../mfc/deriving-a-class-from-cobject.md), `CObject` класс имеет возможность определить точный класс объекта, который во время выполнения.  
  
 Эта возможность полезна при необходимости дополнительного типа, проверяющего аргументов функции, и необходимо написать код специального назначения, на основе класса объекта. Однако такой подход не рекомендуется обычно так, как он применяет функцию виртуальные функции.  
  
 `CObject` Функции-члена `IsKindOf` может использоваться для определения конкретного объекта принадлежит указанный класс, или он является производным от определенного класса. Аргумент `IsKindOf` — `CRuntimeClass` объекта, который вы можно получить с помощью `RUNTIME_CLASS` макрос с именем класса.  
  
### <a name="to-use-the-runtimeclass-macro"></a>Использование макроса RUNTIME_CLASS  
  
1.  Используйте `RUNTIME_CLASS` с именем класса, как показано ниже, для класса `CObject`:  
  
     [!code-cpp[NVC_MFCCObjectSample#4](../mfc/codesnippet/cpp/accessing-run-time-class-information_1.cpp)]  
  
 Потребуется редко напрямую обращаться к такому объекту класса во время выполнения. Чаще всего используется для передачи объекта класса среды выполнения для `IsKindOf` функции, как показано в следующей процедуре. `IsKindOf` Функция проверяет, принадлежит ли он к определенному классу объекта.  
  
#### <a name="to-use-the-iskindof-function"></a>Чтобы использовать функцию IsKindOf  
  
1.  Убедитесь, что у класса имеется поддержка класса среды выполнения. То есть класс должен полученных прямо или косвенно из `CObject` и использовать **DECLARE**_**динамическое** и `IMPLEMENT_DYNAMIC`, `DECLARE_DYNCREATE` и `IMPLEMENT_DYNCREATE`, или `DECLARE_SERIAL` и `IMPLEMENT_SERIAL` макросы описано в статье [наследование класса от CObject](../mfc/deriving-a-class-from-cobject.md).  
  
2.  Вызовите `IsKindOf` функции-члена для объектов этого класса, с помощью `RUNTIME_CLASS` макрос для создания `CRuntimeClass` аргумент, как показано ниже:  
  
     [!code-cpp[NVC_MFCCObjectSample#2](../mfc/codesnippet/cpp/accessing-run-time-class-information_2.h)]  
  
     [!code-cpp[NVC_MFCCObjectSample#5](../mfc/codesnippet/cpp/accessing-run-time-class-information_3.cpp)]  
  
    > [!NOTE]
    >  Возвращает IsKindOf **TRUE** Если объект является членом указанного класса или класса, производного от указанного класса. `IsKindOf`не поддерживает несколько наследования или виртуальными базовыми классами, несмотря на то, что при необходимости можно использовать множественное наследование для производных классов Microsoft Foundation.  
  
 Сведения о классе среды выполнения применяется в динамическое создание объектов. Этот процесс описывается в статье [динамическое создание объектов](../mfc/dynamic-object-creation.md).  
  
 Более подробные сведения о сериализации и сведения о классе во время выполнения, см. в статьях [файлы в MFC](../mfc/files-in-mfc.md) и [сериализации](../mfc/serialization-in-mfc.md).  
  
## <a name="see-also"></a>См. также  
 [Использование CObject](../mfc/using-cobject.md)

