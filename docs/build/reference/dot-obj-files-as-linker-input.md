---
title: ". OBJ-файлы в качестве входных данных компоновщика | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- linker [C++], OBJ files as input
- object files, linker output
- OMF object files
- LINK tool [C++], .obj files
- COFF files
- OBJ files as linker input
- .obj files as linker input
ms.assetid: 3028e423-8b10-4972-8eb4-6e9ae58f0a26
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ca8346f9ff29d097450eda4d8bfbfee7f7a3f522
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="obj-files-as-linker-input"></a>OBJ-файлы в качестве входных файлов компоновщика
Инструмент-компоновщик (ссылка. (EXE) принимает OBJ-файлы, которые в общих объекта файла формат COFF.  
  
## <a name="remarks"></a>Примечания  
 Корпорация Майкрософт предоставляет загружаемый документ, который определяет общий формат файла объекта. Дополнительные сведения, загрузите 8.1 или более поздней [переносимый исполняемый файл Майкрософт и общие спецификации формата файла объекта](http://go.microsoft.com/fwlink/?LinkId=93292).  
  
## <a name="unicode-support"></a>Поддержка Юникода  
 Начиная с Visual Studio 2005, компилятор Microsoft Visual C++ поддерживает символы Юникода в идентификаторах в соответствии с определением ISO/IEC C и C++ стандартов. Предыдущие версии компилятора поддерживается только символы ASCII в качестве идентификаторов. Поддержка Юникода в именах функций, классов и статических переменных, компилятор и компоновщик используют кодировку Юникод UTF-8 для символов COFF в OBJ-файлы. Кодировка UTF-8 восходящая совместим с кодировкой ASCII, используемой в более ранних версиях Visual Studio.  
  
 Дополнительные сведения о компиляторе и компоновщике см. в разделе [поддержка Юникода в компиляторе и компоновщике](../../build/reference/unicode-support-in-the-compiler-and-linker.md). Дополнительные сведения о стандарте Юникод см. в разделе [Юникода](http://go.microsoft.com/fwlink/?LinkId=37123) организации.  
  
## <a name="see-also"></a>См. также  
 [Входные LINK-файлы](../../build/reference/link-input-files.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)   
 [Поддержка Юникода](../../text/support-for-unicode.md)   
 [Поддержка Юникода в компиляторе и компоновщике](../../build/reference/unicode-support-in-the-compiler-and-linker.md)   
 [Стандарт Юникод](http://go.microsoft.com/fwlink/?LinkId=37123)   
 [Общие спецификации формата файла объекта](http://go.microsoft.com/fwlink/?LinkId=93292)