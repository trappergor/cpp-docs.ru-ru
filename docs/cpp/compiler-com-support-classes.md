---
title: "Классы поддержки компилятора COM | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_raise_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe - компилятор, поддержка COM"
  - "COM, поддержка компилятора"
ms.assetid: 6d800d9b-b902-4033-9639-740a30b06f88
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Классы поддержки компилятора COM
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Стандартные классы используются для поддержки некоторых типов модели COM.  Классы определены в файле comdef.h и являются файлами заголовка, созданными из библиотеки типов.  
  
|Класс|Назначение|  
|-----------|----------------|  
|[\_bstr\_t](../cpp/bstr-t-class.md)|Создает программу оболочку для типа `BSTR`, предоставляя полезные операторы и методы.|  
|[\_com\_error](../cpp/com-error-class.md)|Определяет объект ошибки, создаваемый [\_com\_raise\_error](../cpp/com-raise-error.md) в случае большинства сбоев.|  
|[\_com\_ptr\_t](../cpp/com-ptr-t-class.md)|Инкапсулирует указатели COM\-интерфейса и автоматически выполняет необходимые вызовы методов `AddRef`, **Release** и `QueryInterface`.|  
|[\_variant\_t](../cpp/variant-t-class.md)|Создает программу оболочку для типа **VARIANT**, предоставляя полезные операторы и методы.|  
  
## Завершение блока, относящегося только к системам Microsoft  
  
## См. также  
 [Поддержка компилятора COM](../Topic/Compiler%20COM%20Support.md)   
 [Глобальные функции компилятора COM](../cpp/compiler-com-global-functions.md)   
 [Справочник по языку C\+\+](../cpp/cpp-language-reference.md)