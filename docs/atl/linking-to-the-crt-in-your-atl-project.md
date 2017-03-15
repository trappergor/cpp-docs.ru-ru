---
title: "Linking to the CRT in Your ATL Project | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DllMainCRTStartup"
  - "wWinMainCRTStartup"
  - "WinMainCRTStartup"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL - библиотека, C Run-Time library (CRT)"
  - "CRT - библиотека, linking with ATL"
  - "DllMainCRTStartup method"
  - "WinMainCRTStartup method"
  - "wWinMainCRTStartup method"
ms.assetid: 650957ae-362c-4ecf-8b03-5d49138e8b5b
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Linking to the CRT in Your ATL Project
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[Библиотеки времени выполнения C](../c-runtime-library/crt-library-features.md) \(CRT\) предоставляет много полезных функций, которые могут сделать программировании очень простую во время разработки библиотеки ATL.  Все проекты библиотеки ATL ссылаются на библиотеке CRT.  Можно видеть преимущества и недостатки метода связывания в [Преимущества и уступки метода, используемого для связывания с CRT](../atl/benefits-and-tradeoffs-of-the-method-used-to-link-to-the-crt.md).  
  
## Влияние связывания с CRT в собственном режиме программы  
 Если статически связываются с CRT, то код из CRT помещается в исполняемом образом, нет необходимости использовать библиотеку DLL CRT присутствует в системе, чтобы начать выполнение образа.  Если динамически связанный с CRT, ссылки на код в библиотеку DLL CRT помещаются в собственном режиме, но не коде.  Для этого в образ для запуска данной системе, библиотека DLL CRT должен присутствовать на этой системе.  Даже если связанный с динамически CRT, можно обнаружить, что некоторый код можно статически связать \(например, **DllMainCRTStartup**\).  
  
 При связывании в образ, либо явно или неявно указать точку входа, будут вызывать после загрузки образа операционной системы.  Для библиотеки DLL по умолчанию точка входа **DllMainCRTStartup**.  Для EXE, это **WinMainCRTStartup**.  Значение по умолчанию можно переопределить с помощью параметра компоновщика \/ENTRY.  Библиотека CRT предоставляет реализацию для **DllMainCRTStartup**, **WinMainCRTStartup** и **wWinMainCRTStartup** \(точки входа Юникода для EXE\).  Эти конструкторы, предоставляемые CRT\- вызова точки входа для глобальных объектов и инициализируют другие структуры данных, которые используются в определенных функций CRT.  Этот код добавляет о 25K запуска в образу если он связывание статической.  Если связать динамически, то большая часть кода в библиотеке DLL, поэтому свой размер образа остается небольшим.  
  
 Дополнительные сведения см. в разделе [\/ENTRY \(Символ точки входа\)](../build/reference/entry-entry-point-symbol.md) компоновщика.  
  
## Параметры оптимизации  
 С помощью параметра \/OPT компоновщика: Далее NOWIN98 может уменьшить по умолчанию элемент управления библиотеки ATL 10K за счет повышения срабатывания загрузки в системах Windows 98.  Дополнительные сведения о параметрах связывания см. в разделе [\/OPT \(Оптимизация\)](../build/reference/opt-optimizations.md).  
  
## См. также  
 [Программирование с использованием ATL и кода среды выполнения C](../atl/programming-with-atl-and-c-run-time-code.md)   
 [Поведение библиотеки времени выполнения](../build/run-time-library-behavior.md)