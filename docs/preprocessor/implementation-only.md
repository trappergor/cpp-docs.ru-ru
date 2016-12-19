---
title: "implementation_only | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "implementation_only"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "implementation_only - атрибут"
ms.assetid: d8cabc86-4425-45a0-9587-d57536980088
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# implementation_only
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к языку C\+\+**  
  
 Отключает создание файла заголовка .tlh \(основного файла заголовка\).  
  
## Синтаксис  
  
```  
implementation_only  
```  
  
## Заметки  
 Этот файл содержит все объявления, используемые для предоставления содержимого библиотек типов.  Будет создан и включен в компиляцию файл заголовка .tli, содержащий реализации функций\-членов оболочки.  
  
 Если этот атрибут указан, содержимое заголовка .tli находится в том же пространстве имен, которое обычно используется в заголовке .tlh.  Кроме того, функции\-члены не объявляются как встроенные.  
  
 Атрибут `implementation_only` предназначен для использования в сочетании с атрибутом [no\_implementation](../preprocessor/no-implementation.md), чтобы исключить хранение реализаций в файле предварительно откомпилированного заголовка \(PCH\).  Оператор `#import` с атрибутом `no_implementation` размещается в области исходного кода, использованной для создания файла PCH.  Получающийся файл PCH используется несколькими файлами исходного кода.  Затем оператор `#import` с атрибутом `implementation_only` используется вне области PCH.  Этот оператор можно использовать только один раз в одном из файлов исходного кода.  При этом будут созданы все необходимые функции\-члены оболочки без дополнительной повторной компиляции каждого файла исходного кода.  
  
> [!NOTE]
>  Атрибут `implementation_only` в одном операторе `#import` должен использоваться вместе с другим оператором `#import` для той же библиотеки типов с атрибутом `no_implementation`.  В противном случае возникнут ошибки компилятора.  Это происходит потому, что определения класса\-оболочки, создаваемые оператором `#import` с атрибутом `no_implementation`, должны компилировать реализации, создаваемые атрибутом `implementation_only`.  
  
 **Завершение блока, относящегося только к языку C\+\+**  
  
## См. также  
 [Атрибуты \#import](../preprocessor/hash-import-attributes-cpp.md)   
 [Директива \#import](../Topic/%23import%20Directive%20\(C++\).md)