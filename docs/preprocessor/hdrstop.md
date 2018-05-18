---
title: hdrstop | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- hdrstop_CPP
- vc-pragma.hdrstop
dev_langs:
- C++
helpviewer_keywords:
- hdrstop pragma
- pragmas, hdrstop
ms.assetid: 5ea8370a-10d1-4538-ade6-4c841185da0e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f1c628efaf45be87dcfc046cf1774c762c157f4f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="hdrstop"></a>hdrstop
Предоставляет дополнительный контроль над именами файлов предварительной компиляции и расположении сохранения состояния компиляции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
#pragma hdrstop [( "filename" )]    
```  
  
## <a name="remarks"></a>Примечания  
 *Filename* имя предкомпилированного файла заголовка для использования или создать (в зависимости от того, следует ли [/Yu](../build/reference/yu-use-precompiled-header-file.md) или [/Yc](../build/reference/yc-create-precompiled-header-file.md) указан). Если *filename* не содержит спецификацию пути, предкомпилированный файл заголовка считается в том же каталоге, что и исходный файл.  
  
 Если файл C или C++ содержит **hdrstop** pragma при компиляции с параметром/Yc, компилятор сохраняет состояние компиляции до расположения этой директивы. Скомпилированное состояние любого кода, следующего за директивой pragma, не сохраняется.  
  
 Используйте *filename* имя для файла предкомпилированного заголовка, в котором сохраняется компилированное состояние. Пробел между **hdrstop** и *filename* является необязательным. Имя файла, указанное в **hdrstop** pragma является строкой и поэтому могут применяться ограничения любой строки C или C++. В частности следует заключать его в кавычки и использовать escape-символ (обратную косую черту) для задания имен каталогов. Пример:  
  
```  
#pragma hdrstop( "c:\\projects\\include\\myinc.pch" )  
```  
  
 Имя предкомпилированного файла заголовка определяется в соответствии со следующим правилам в порядке приоритета.  
  
1.  Аргумент параметра компилятора /Fp  
  
2.  *Filename* аргумент #**директивы #pragma hdrstop**  
  
3.  Базовое имя файла исходного кода с расширением .PCH  
  
 Для параметров компилятора /Yc и /Yu параметров, если ни один из параметров компиляции два ни **hdrstop** pragma указывает имя файла, базовое имя исходного файла используется как базовое имя файла предкомпилированного заголовка.  
  
 Команды предварительной обработки также можно использовать для выполнения замены макроса.  
  
```  
#define INCLUDE_PATH "c:\\progra~`1\\devstsu~1\\vc\\include\\"  
#define PCH_FNAME "PROG.PCH"  
.  
.  
.  
#pragma hdrstop( INCLUDE_PATH PCH_FNAME )  
```  
  
 Следующие правила определяют, где **hdrstop** можно поместить директиву pragma:  
  
-   Она должна находится за пределами любых объявлений или определений данных или функций.  
  
-   Она должна задаваться в файле исходного кода, а не заголовка.  
  
## <a name="example"></a>Пример  
  
```  
#include <windows.h>                 // Include several files  
#include "myhdr.h"  
  
__inline Disp( char *szToDisplay )   // Define an inline function  
{  
    ...                              // Some code to display string  
}  
#pragma hdrstop  
```  
  
 В этом примере **hdrstop** pragma отображается после двух файлов, которые были включены и встроенной функции определен. Поначалу такое расположение директивы pragma может показаться странным. Однако рассмотрим, что при использовании параметров предварительной компиляции вручную, /Yc и /Yu с **hdrstop** pragma позволяет выполнить предварительную компиляцию все исходные файлы, включая встроенный код. Компилятор Microsoft не ограничивает предварительную компиляцию только объявлениями данных.  
  
## <a name="see-also"></a>См. также  
 [Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)