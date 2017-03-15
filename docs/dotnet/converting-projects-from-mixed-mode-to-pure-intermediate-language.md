---
title: "Преобразование проектов из смешанного режима в чистый промежуточный язык | Microsoft Docs"
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
  - "промежуточный язык, приложения в смешанном режиме"
  - "приложения в смешанном режиме"
  - "приложения в смешанном режиме, промежуточный язык"
  - "проекты [C++], конвертирование в промежуточный язык"
ms.assetid: 855f9e3c-4f09-4bfe-8eab-a45f68292be9
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Преобразование проектов из смешанного режима в чистый промежуточный язык
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Все проекты среды CLR Visual C\+\+ по умолчанию ссылаются на библиотеки времени выполнения C.  Следовательно, эти проекты классифицируются как приложения смешанного режима, поскольку в них объединяется машинный код и код, предназначенный для среды CLR \(т.е. управляемый код\).  Они компилируются в промежуточный язык \(IL\), также называемый языком MSIL.  
  
### Преобразование проектов из смешанного режима в чистый промежуточный язык  
  
1.  Удалите ссылки на [библиотеки времени выполнения C](../c-runtime-library/crt-library-features.md) \(CRT\):  
  
    1.  В CPP\-файле, определяющем точку входа приложения, измените точку входа на `Main()`.  Значение `Main()` указывает, что данный проект не ссылается на CRT.  
  
    2.  В обозревателе решений щелкните правой кнопкой мыши проект и выберите в контекстном меню пункт **Свойства**, чтобы открыть страницы свойств приложения.  
  
    3.  На странице свойств **Дополнительно** узла **Компоновщика** проекта введите для параметра **точка входа** значение **Main**.  
  
    4.  Для консольных приложений на странице свойств **Система** узла **Компоновщика** проекта выберите поле **Подсистема** и измените его значение на **Console \(\/SUBSYSTEM:CONSOLE\)**.  
  
        > [!NOTE]
        >  Для приложений Windows Forms это свойство устанавливать не нужно, поскольку поле **Подсистема** по умолчанию имеет значение **Windows \(\/SUBSYSTEM:WINDOWS\)**.  
  
    5.  В файле stdafx.h закомментируйте все операторы `#include`.  Например, в консольных приложениях:  
  
        ```  
        // #include <iostream>  
        // #include <tchar.h>  
        ```  
  
         – или –  
  
         В приложениях Windows Forms:  
  
        ```  
        // #include <stdlib.h>  
        // #include <malloc.h>  
        // #include <memory.h>  
        // #include <tchar.h>  
        ```  
  
    6.  Для приложений Windows Forms в файле Form1.cpp закомментируйте оператор `#include`, который ссылается на файл windows.h.  Примеры.  
  
        ```  
        // #include <windows.h>  
        ```  
  
2.  Добавьте в файл stdafx.h следующий код:  
  
    ```  
    #ifndef __FLTUSED__  
    #define __FLTUSED__  
       extern "C" __declspec(selectany) int _fltused=1;  
    #endif  
    ```  
  
3.  Удалите все неуправляемые типы:  
  
    1.  Везде, где это возможно, замените неуправляемые типы ссылками на структуры из пространства имен [System](https://msdn.microsoft.com/en-us/library/system.appdomainmanager.appdomainmanager.aspx).  Основные управляемые типы перечислены в следующей таблице.  
  
        |Структура|Описание|  
        |---------------|--------------|  
        |[\<caps:sentence id\="tgt24" sentenceid\="84e2c64f38f78ba3ea5c905ab5a2da27" class\="tgtSentence"\>Boolean\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.boolean\(v=vs.140\).aspx)|Представляет логическое значение.|  
        |[\<caps:sentence id\="tgt26" sentenceid\="40ea57d3ee3c07bf1c102b466e1c3091" class\="tgtSentence"\>Byte\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.byte\(v=vs.140\).aspx)|Представляет 8\-битовое целое число без знака.|  
        |[\<caps:sentence id\="tgt28" sentenceid\="a87deb01c5f539e6bda34829c8ef2368" class\="tgtSentence"\>Char\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.char\(v=vs.140\).aspx)|Представляет символ Юникода.|  
        |[\<caps:sentence id\="tgt30" sentenceid\="dfeaaeb4316477bd556ea5e8c3295887" class\="tgtSentence"\>DateTime\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.datetime.datetime.aspx)|Представляет текущее время, обычно выраженное как дата и время суток.|  
        |[\<caps:sentence id\="tgt32" sentenceid\="bdaa3c20a3e3851599514f7c6be5f62f" class\="tgtSentence"\>Десятичный\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.decimal\(v=vs.140\).aspx)|Представляет десятичное число.|  
        |[\<caps:sentence id\="tgt34" sentenceid\="e8cd7da078a86726031ad64f35f5a6c0" class\="tgtSentence"\>Double\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.double\(v=vs.140\).aspx)|Представляет число двойной точности с плавающей запятой.|  
        |[\<caps:sentence id\="tgt36" sentenceid\="1e0ca5b1252f1f6b1e0ac91be7e7219e" class\="tgtSentence"\>Guid\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.guid\(v=vs.140\).aspx)|Представляет глобальный уникальный идентификатор \(GUID\).|  
        |[\<caps:sentence id\="tgt38" sentenceid\="ce80d5ec65b1d2a2f1049eadc100db23" class\="tgtSentence"\>Int16\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.int16\(v=vs.140\).aspx)|Представляет 16\-разрядное целое число со знаком.|  
        |[\<caps:sentence id\="tgt40" sentenceid\="0241adbbd83925f051b694d40f02747f" class\="tgtSentence"\>Int32\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.int32\(v=vs.140\).aspx)|Представляет 32\-разрядное целое число со знаком.|  
        |[\<caps:sentence id\="tgt42" sentenceid\="ff9b3f96d37353c528517bc3656a00a8" class\="tgtSentence"\>Int64\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.int64\(v=vs.140\).aspx)|Представляет 64\-разрядное целое число со знаком.|  
        |[\<caps:sentence id\="tgt44" sentenceid\="7f1db863563907cf33604ed7fad6b111" class\="tgtSentence"\>IntPtr;\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.intptr\(v=vs.140\).aspx)|Определяемый платформой тип, который используется для представления указателя или дескриптора.|  
        |[\<caps:sentence id\="tgt46" sentenceid\="943756eb7841efcc43b7cd37d7254c76" class\="tgtSentence"\>SByte\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.byte.aspx)|Представляет 8\-разрядное целое число со знаком.|  
        |[\<caps:sentence id\="tgt48" sentenceid\="dd5c07036f2975ff4bce568b6511d3bc" class\="tgtSentence"\>Single\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.single.aspx)|Представляет число одиночной точности с плавающей запятой.|  
        |[\<caps:sentence id\="tgt50" sentenceid\="90150402997ea9c8dc45cc4d41bb28cb" class\="tgtSentence"\>TimeSpan\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.timespan\(v=vs.140\).aspx)|Представляет интервал времени.|  
        |[\<caps:sentence id\="tgt52" sentenceid\="a00ef2ef85ff67b7b39339886f19044f" class\="tgtSentence"\>UInt16\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.uint16\(v=vs.140\).aspx)|Представляет беззнаковое 16\-разрядное целое число.|  
        |[\<caps:sentence id\="tgt54" sentenceid\="3de84ad0700f2a1571f633d399e1900e" class\="tgtSentence"\>UInt32\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.uint32\(v=vs.140\).aspx)|Представляет беззнаковое 32\-разрядное целое число.|  
        |[\<caps:sentence id\="tgt56" sentenceid\="2e8d31865e5d4b9d8611e1b991baed07" class\="tgtSentence"\>UInt64\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.uint64\(v=vs.140\).aspx)|Представляет беззнаковое 64\-битовое целое число.|  
        |[\<caps:sentence id\="tgt58" sentenceid\="92d74abda31865424016b16e2c806a66" class\="tgtSentence"\>UIntPtr\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.uintptr\(v=vs.140\).aspx)|Определяемый платформой тип, который используется для представления указателя или дескриптора.|  
        |[\<caps:sentence id\="tgt60" sentenceid\="cab8111fd0b710a336c898e539090e34" class\="tgtSentence"\>Void\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.void\(v=vs.140\).aspx)|Указывает метод, который не возвращает значение, т.е. метод, который имеет тип возвращаемого значения "Void".|