---
title: "Доступ к сведениям о классе во время выполнения | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "классы [C++], сведения о классе среды выполнения"
  - "CObject - класс, доступ к сведениям о классе среды выполнения"
  - "CObject - класс, и RTTI"
  - "CObject - класс, использование метода IsKindOf"
  - "CObject - класс, использование макроса RUNTIME_CLASS"
  - "IsKindOf - метод"
  - "RTTI - параметр компилятора"
  - "время выполнения"
  - "время выполнения, сведения о классах"
  - "класс среды выполнения"
  - "класс среды выполнения, доступ к сведениям"
  - "RUNTIME_CLASS - макрос"
  - "RUNTIME_CLASS - макрос, использование"
ms.assetid: 3445a9af-0bd6-4496-95c3-aa59b964570b
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Доступ к сведениям о классе во время выполнения
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В этой статье описывается, как получить сведения о классе объекта во время выполнения.  
  
> [!NOTE]
>  MFC не использует введенную поддержку [Данные типа во время выполнения](../Topic/Run-Time%20Type%20Information.md) \(RTTI\) C в Visual C\+\+ 4.0.  
  
 Если производного класса из [CObject](../Topic/CObject%20Class.md) и задан \_**динамические** и `IMPLEMENT_DYNAMIC`, `DECLARE_DYNCREATE` и `IMPLEMENT_DYNCREATE`**declare** или проверки, описанных макросы `DECLARE_SERIAL` и `IMPLEMENT_SERIAL` в статье [Производный класс от CObject](../mfc/deriving-a-class-from-cobject.md), класс `CObject` имеет возможность определить точный класс объекта во время выполнения.  
  
 Эта возможность особенно полезен, если некоторую проверку типов аргументов функции требуется и когда необходимо написать код одноцелевой на основе класса объекта.  Однако такой подход обычно не рекомендуется, поскольку она дублирует функция виртуальных функций.  
  
 Функции\-члена `IsKindOf``CObject` можно использовать, чтобы определить, совпадает ли указанный объект принадлежит к указанному классу или если он является производным от определенного класса.  Аргумент `IsKindOf` объект `CRuntimeClass`, можно получить с помощью макроса `RUNTIME_CLASS` с именем класса.  
  
### Использовать макрос RUNTIME\_CLASS  
  
1.  Используйте `RUNTIME_CLASS` с именем класса, как показано ниже для класса `CObject`:  
  
     [!code-cpp[NVC_MFCCObjectSample#4](../mfc/codesnippet/CPP/accessing-run-time-class-information_1.cpp)]  
  
 Для редко бывает необходимо получить объект класса среды выполнения напрямую.  Более распространенным применением передать объект класса среды выполнения функции `IsKindOf`, как показано в следующей процедуре.  Функциональных тестов `IsKindOf` объект, является ли он относится к определенному классу.  
  
#### Использовать функцию IsKindOf  
  
1.  Убедитесь, что класс поддерживает класса среды выполнения.  То есть, класс должен быть производным прямо или косвенно от `CObject`, \_**динамические** и `IMPLEMENT_DYNAMIC`, `DECLARE_DYNCREATE` и `IMPLEMENT_DYNCREATE`**declare** или проверки, описанных макросы `DECLARE_SERIAL` и `IMPLEMENT_SERIAL` в статье [Производный класс от CObject](../mfc/deriving-a-class-from-cobject.md).  
  
2.  Вызовите функцию\-член `IsKindOf` для объектов этого класса с помощью макроса `RUNTIME_CLASS` для создания аргумент `CRuntimeClass`, как показано ниже:  
  
     [!code-cpp[NVC_MFCCObjectSample#2](../mfc/codesnippet/CPP/accessing-run-time-class-information_2.h)]  
  
     [!code-cpp[NVC_MFCCObjectSample#5](../mfc/codesnippet/CPP/accessing-run-time-class-information_3.cpp)]  
  
    > [!NOTE]
    >  IsKindOf возвращает значение **TRUE**, если объект члена заданного класса или класса, производного от указанного класса.  `IsKindOf` не поддерживает множественное наследование или виртуальных базовых классов, хотя множественное наследование можно использовать для создания производных классов библиотеки Microsoft Foundation соответственно.  
  
 Один для данных класса среды выполнения в динамическом создании объекта.  Этот процесс см. в статье [Динамическое создание объектов](../Topic/Dynamic%20Object%20Creation.md).  
  
 Более подробные сведения о сериализации и данные класса среды выполнения см. в статье [Файлы в MFC](../mfc/files-in-mfc.md) и [Сериализация](../Topic/Serialization%20in%20MFC.md).  
  
## См. также  
 [Использование CObject](../mfc/using-cobject.md)