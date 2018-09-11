---
title: hdrstop | Документация Майкрософт
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
ms.openlocfilehash: 10365b4cbe43863f72b721665ae8ea518e3fdc5f
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2018
ms.locfileid: "42540068"
---
# <a name="hdrstop"></a>hdrstop
Предоставляет дополнительный контроль над именами файлов предварительной компиляции и расположении сохранения состояния компиляции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#pragma hdrstop [( "filename" )]    
```  
  
## <a name="remarks"></a>Примечания  
 
*Filename* имя предкомпилированного файла заголовка или создать (в зависимости от того [/Yu](../build/reference/yu-use-precompiled-header-file.md) или [/Yc](../build/reference/yc-create-precompiled-header-file.md) указан). Если *filename* не содержит спецификацию пути предкомпилированного файла заголовка предполагается, что в том же каталоге, что и исходный файл.  
  
Если файл C или C++ содержит **hdrstop** pragma при компиляции с `/Yc`, компилятор сохраняет состояние компиляции до расположения этой директивы. Скомпилированное состояние любого кода, следующего за директивой pragma, не сохраняется.  
  
Используйте *filename* имя для файла предкомпилированного заголовка, в котором сохраняется компилированное состояние. Пробел между **hdrstop** и *filename* является необязательным. Имя файла, указанное в **hdrstop** pragma — это строка, поэтому в соответствии с ограничениями любая строка C или C++. В частности следует заключать его в кавычки и использовать escape-символ (обратную косую черту) для задания имен каталогов. Пример:  
  
```  
#pragma hdrstop( "c:\\projects\\include\\myinc.pch" )  
```  
  
Имя предкомпилированного файла заголовка определяется в соответствии со следующим правилам в порядке приоритета.  
  
1. Аргумент `/Fp` параметр компилятора  
  
2. *Filename* аргумента `#pragma hdrstop`  
  
3. Базовое имя файла исходного кода с расширением .PCH  
  
Для `/Yc` и `/Yu` параметры, если ни один из двух параметров компиляции, ни **hdrstop** директива pragma указывает имя файла, базовое имя исходного файла используется в качестве базового имени предкомпилированного файла заголовка.  
  
Команды предварительной обработки также можно использовать для выполнения замены макроса.  
  
```  
#define INCLUDE_PATH "c:\\progra~`1\\devstsu~1\\vc\\include\\"  
#define PCH_FNAME "PROG.PCH"  
.  
.  
.  
#pragma hdrstop( INCLUDE_PATH PCH_FNAME )  
```  
  
Следующие правила определяют местоположение **hdrstop** директивы pragma:  
  
- Она должна находится за пределами любых объявлений или определений данных или функций.  
  
- Она должна задаваться в файле исходного кода, а не заголовка.  
  
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
  
В этом примере **hdrstop** pragma появляется после два файла должны быть добавлены и встроенная функция был определен. Поначалу такое расположение директивы pragma может показаться странным. Обратите внимание, однако с помощью параметров предварительной компиляции вручную, `/Yc` и `/Yu`, с помощью **hdrstop** pragma позволяет выполнять предварительную компиляцию файлов исходного кода целиком, включая встроенный код. Компилятор Microsoft не ограничивает предварительную компиляцию только объявлениями данных.  
  
## <a name="see-also"></a>См. также  
 
[Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)