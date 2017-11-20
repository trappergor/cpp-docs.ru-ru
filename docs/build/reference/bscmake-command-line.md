---
title: "Командная строка BSCMAKE | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: BSCMAKE, command line
ms.assetid: 8006e8cf-8bfe-4c23-868a-b0a25e6bbf0f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 278518ae37a4e76ea4fe0252e3341e54daebe599
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="bscmake-command-line"></a>Командная строка BSCMAKE
Чтобы запускать BSCMAKE, используйте следующий синтаксис командной строки:  
  
```  
BSCMAKE [options] sbrfiles  
```  
  
 Параметры могут находиться только в `options` в командной строке.  
  
 *Sbrfiles* поле указывает один или несколько SBR-файлы, созданные компилятором или ассемблером. Имена SBR-файлы должны разделяться пробелами или знаками табуляции. Необходимо указать расширение; по умолчанию отсутствует. Можно указать путь с именем файла, а также можно использовать подстановочные знаки операционной системы (* и?).  
  
 Во время добавочной сборки можно указать новые SBR-файлы, которые не были частью исходной сборки. Если требуется, чтобы все вносимые в файла для просмотра информации, необходимо указать все SBR-файлы (включая усеченные файлы), которые изначально использовались для создания BSC-файл. Если опустить SBR-файл, его вклад в файл для файла для просмотра информации удаляется.  
  
 Не указывайте усеченный SBR-файл для полной сборки. Полное построение используются вклады всех указанных SBR-файлов. Прежде чем выполнять полное построение, Перекомпилируйте проект и создать новый SBR-файл для каждого пустого файла.  
  
 Следующая команда выполняет BSCMAKE для построения файла main.BSC из трех SBR-файлов:  
  
```  
BSCMAKE main.sbr file1.sbr file2.sbr  
```  
  
 Дополнительные сведения см. в разделе [командный файл BSCMAKE](../../build/reference/bscmake-command-file-response-file.md) и [параметры BSCMAKE](../../build/reference/bscmake-options.md).  
  
## <a name="see-also"></a>См. также  
 [Справочник ВSCMAKE](../../build/reference/bscmake-reference.md)