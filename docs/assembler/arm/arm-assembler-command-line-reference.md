---
title: "ARM Assembler Command-Line Reference | Microsoft Docs"
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
ms.assetid: f7b89478-1ab5-4995-8cde-a805f0462c45
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ARM Assembler Command-Line Reference
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Эта статья содержит сведения об ассемблер Microsoft ARM  *armasm*, который компилирует ARMv7 Thumb язык ассемблера в реализацией общих объектов формата файла \(COFF\).  Компоновщик можно связать COFF код с кодом объекта, созданного по ассемблер ARM, компилятор c с помощью библиотеки объектов, которые были созданы библиотекаря.  
  
## Синтаксис  
  
```  
armasm [[options]] sourcefile objectfile  
```  
  
```  
armasm [[options]] -o objectfile sourcefile  
```  
  
#### Параметры  
 `options`  
 \-ошибки`filename`  
 Перенаправить сообщения ошибок и предупреждений для `filename`.  
  
 \-i`dir[;dir]`  
 Добавьте путь поиска включаемых указанные папки.  
  
 \-входящими звонками`directive`  
 Укажите директиву SETA, SETL или НАБОРЫ для опознания символа.  Пример: **armasm.exe \-predefine "COUNT SETA 150" source.asm**.  Для получения дополнительных сведений см. [средства ассемблер ARM руководство](http://go.microsoft.com/fwlink/?LinkId=246102).  
  
 \-nowarn  
 Отключите все предупреждения.  
  
 \-игнорировать`warning`  
 Отключите указанное предупреждение.  Возможные значения в разделе сведения о предупреждениях.  
  
 \-Справка  
 Печать сообщения справку командной строки.  
  
 \-машины`machine`  
 Укажите тип компьютера в заголовке PE.  Возможные значения для `machine` являются:   
**ARM**— Задает тип машины IMAGE\_FILE\_MACHINE\_ARMNT.  Это значение по умолчанию.   
**THUMB**— Задает тип машины IMAGE\_FILE\_MACHINE\_THUMB.  
  
 \-oldit  
 Создание стиля ARMv7 ИНФОРМАЦИОННЫХ блоков.  По умолчанию, ARMv8\-совместимый созданных ИНФОРМАЦИОННЫХ блоков.  
  
 \-через`filename`  
 Чтение дополнительных аргументов командной строки из `filename`.  
  
 \-16  
 Создание источника как 16\-разрядные инструкции Thumb.  Это значение по умолчанию.  
  
 \-32  
 Создание источника как 32\-разрядных инструкций ARM.  
  
 \-g  
 Создает отладочную информацию.  
  
 \-errorReport:`option`  
 Укажите, как внутренние ассемблер, сообщение об ошибке в корпорацию Майкрософт.  Возможные значения для `option` являются:   
**none**— Не отправлять отчеты.   
**prompt**— Запрос пользователя на отправку отчетов немедленно.   
**queue**— Запрос на отправку отчетов при следующем входе администратора.  Это значение по умолчанию.   
**send**— Автоматически отправьте отчеты.  
  
 `sourcefile`  
 Имя исходного файла.  
  
 `objectfile`  
 Имя файла объекта \(output\).  
  
 Следующий пример демонстрирует использование armasm в типичном сценарии.  Во\-первых можно используйте armasm для создания файла источника \(.asm\) языка ассемблера объектный OBJ\-файл.  Затем с помощью командной строки компилятора C CL для компиляции файла источника \(.c\) и также указать параметр компоновщика для связи файла объекта ARM.  
  
 **armasm myasmcode.asm \-o myasmcode.obj**  
  
 **cl myccode.c \/link myasmcode.obj**  
  
## См. также  
 [ARM Assembler Diagnostic Messages](../../assembler/arm/arm-assembler-diagnostic-messages.md)   
 [ARM Assembler Directives](../../assembler/arm/arm-assembler-directives.md)