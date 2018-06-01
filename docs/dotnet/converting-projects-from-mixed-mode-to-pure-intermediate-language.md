---
title: Преобразование проектов из смешанного режима в чистый промежуточный язык | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- intermediate language, mixed-mode applications
- mixed-mode applications
- mixed-mode applications, intermediate language
- projects [C++], converting to intermediate language
ms.assetid: 855f9e3c-4f09-4bfe-8eab-a45f68292be9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 98560841b40b7bb4691222dfa254f06a071b07da
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704637"
---
# <a name="converting-projects-from-mixed-mode-to-pure-intermediate-language"></a>Преобразование проектов из смешанного режима в чистый промежуточный язык

Все проекты Visual C++ CLR ссылки на библиотеки времени выполнения C по умолчанию. Следовательно эти проекты классифицируются как приложения в смешанном режиме, поскольку в них объединяется машинный код с кодом языка среды CLR (управляемого кода). При компиляции, они компилируются в промежуточный язык (IL), также известный как промежуточный язык Майкрософт (MSIL).

> [!IMPORTANT]
> Рекомендуется использовать Visual Studio 2015 и Visual Studio 2017 г больше не поддерживает создание **/CLR: pure** или **/CLR: safe** кода для приложений со средой CLR. Если требуется чистого и безопасного сборки, рекомендуется перевести приложения на C#.

При использовании более ранней версии инструментов компилятора Visual C++, который поддерживает **/CLR: pure** или **/CLR: safe**, эту процедуру можно использовать для преобразования кода в чистый MSIL:

### <a name="to-convert-your-mixed-mode-application-into-pure-intermediate-language"></a>Для преобразования приложения смешанного режима в чистый промежуточный язык

1. Удалите ссылки на [библиотеки времени выполнения C](../c-runtime-library/crt-library-features.md) (CRT):

   1. В CPP-файле, определяющем точку входа приложения, изменить точку входа `Main()`. С помощью `Main()` указывает, что проект ссылается на CRT.

   2. В обозревателе решений щелкните правой кнопкой мыши проект и выберите **свойства** в контекстном меню, чтобы открыть страницы свойств для приложения.

   3. В **Дополнительно** страницы свойств проекта для **компоновщика**выберите **точки входа** , а затем введите **Main** в этом поле.

   4. Для консольных приложений в **системы** страницы свойств проекта для **компоновщика**выберите **подсистемы** поле и измените его значение на **консоли (/ SUBSYSTEM:Console)**.

      > [!NOTE]
      > Необходимо задать это свойство для приложений Windows Forms, так как **подсистемы** имеет значение **Windows (/ SUBSYSTEM: WINDOWS)** по умолчанию.

   5. Добавьте в файл stdafx.h закомментируйте все `#include` инструкции. Например в консольных приложениях:

      ```cpp
      // #include <iostream>
      // #include <tchar.h>
      ```

       - или -

       Например в приложениях Windows Forms:

      ```cpp
      // #include <stdlib.h>
      // #include <malloc.h>
      // #include <memory.h>
      // #include <tchar.h>
      ```

   6. Для приложений Windows Forms, в Form1.cpp, закомментируйте `#include` инструкцию, которая ссылается на windows.h. Пример:

      ```cpp
      // #include <windows.h>
      ```

2. Добавьте следующий код в файле stdafx.h:

   ```cpp
   #ifndef __FLTUSED__
   #define __FLTUSED__
      extern "C" __declspec(selectany) int _fltused=1;
   #endif
   ```

3. Удалите все неуправляемые типы:

   Везде, где это возможно, замените неуправляемые типы ссылками на структуры из [системы](https://msdn.microsoft.com/en-us/library/system.appdomainmanager.appdomainmanager.aspx) пространства имен. В следующей таблице перечислены распространенные управляемых типов.

   |Структура|Описание:|
   |---------------|-----------------|
   |[Boolean](https://msdn.microsoft.com/en-us/library/system.boolean\(v=vs.140\).aspx)|Представляет логическое значение.|
   |[Byte](https://msdn.microsoft.com/en-us/library/system.byte\(v=vs.140\).aspx)|Представляет 8-битовое целое число без знака.|
   |[Char](https://msdn.microsoft.com/en-us/library/system.char\(v=vs.140\).aspx)|Представляет символ Юникода.|
   |[DateTime](https://msdn.microsoft.com/en-us/library/system.datetime.datetime.aspx)|Представляет текущее время, обычно выраженное как дата и время суток.|
   |[Decimal](https://msdn.microsoft.com/en-us/library/system.decimal\(v=vs.140\).aspx)|Представляет десятичное число.|
   |[Double](https://msdn.microsoft.com/en-us/library/system.double\(v=vs.140\).aspx)|Представляет число двойной точности с плавающей запятой.|
   |[Guid](https://msdn.microsoft.com/en-us/library/system.guid\(v=vs.140\).aspx)|Представляет глобальный уникальный идентификатор (GUID).|
   |[Int16](https://msdn.microsoft.com/en-us/library/system.int16\(v=vs.140\).aspx)|Представляет 16-разрядное целое число со знаком.|
   |[Int32](https://msdn.microsoft.com/en-us/library/system.int32\(v=vs.140\).aspx)|Представляет 32-разрядное целое число со знаком.|
   |[Int64](https://msdn.microsoft.com/en-us/library/system.int64\(v=vs.140\).aspx)|Представляет 64-разрядное целое число со знаком.|
   |[IntPtr](https://msdn.microsoft.com/en-us/library/system.intptr\(v=vs.140\).aspx)|Определяемый платформой тип, который используется для представления указателя или дескриптора.|
   |[SByte](https://msdn.microsoft.com/en-us/library/system.byte.aspx)|Представляет 8-разрядное целое число со знаком.|
   |[Single](https://msdn.microsoft.com/en-us/library/system.single.aspx)|Представляет число с плавающей запятой одиночной точности.|
   |[TimeSpan](https://msdn.microsoft.com/en-us/library/system.timespan\(v=vs.140\).aspx)|Представляет интервал времени.|
   |[UInt16](https://msdn.microsoft.com/en-us/library/system.uint16\(v=vs.140\).aspx)|Представляет 16-битовое целое число без знака.|
   |[UInt32](https://msdn.microsoft.com/en-us/library/system.uint32\(v=vs.140\).aspx)|Представляет 32-битовое целое число без знака.|
   |[UInt64](https://msdn.microsoft.com/en-us/library/system.uint64\(v=vs.140\).aspx)|Представляет 64-битовое целое число без знака.|
   |[UIntPtr](https://msdn.microsoft.com/en-us/library/system.uintptr\(v=vs.140\).aspx)|Определяемый платформой тип, который используется для представления указателя или дескриптора.|
   |[значение типа void](https://msdn.microsoft.com/en-us/library/system.void\(v=vs.140\).aspx)|Указывает метод, который не возвращает значений. то есть метод имеет тип возврата void.|