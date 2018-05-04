---
title: -Fi (Предварительная обработка имени выходного файла) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Fi
dev_langs:
- C++
helpviewer_keywords:
- Fi compiler option (C++)
- -Fi compiler option (C++)
- /Fi compiler option (C++)
- preprocessing output files, file name
ms.assetid: 6d0ba983-a8b7-41ec-84f5-b4688ef8efee
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0e7fe5ffbb8a6ccdd5ef02d2cf3feb6b94d48233
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="fi-preprocess-output-file-name"></a>/Fi (предварительная обработка имени выходного файла)
Задает имя выходного файла, к которому [/P (Предварительная обработка в файл)](../../build/reference/p-preprocess-to-a-file.md) параметр компилятора записывает предварительно обработанные выходные данные.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/Fipathname  
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`pathname`|Имя и путь выходного файла, созданного **/P** параметр компилятора.|  
  
## <a name="remarks"></a>Примечания  
 Используйте **/Fi** параметра компилятора в сочетании с **/P** параметр компилятора.  
  
 Если указать только путь для `pathname` , базовое имя исходного файла используется в качестве базового имени файла предварительно обработанные выходные данные. `pathname` Расширение имени файла, определенного для параметра не требуется. Тем не менее если не указать расширение имени файла, используется расширение «i».  
  
## <a name="example"></a>Пример  
 Следующая командная строка предварительно обрабатывает PROGRAM.cpp, сохраняет комментарии, добавляет [#line](../../preprocessor/hash-line-directive-c-cpp.md) директив и записывает результаты в файл MYPROCESS.i.  
  
```  
CL /P /FiMYPROCESS.I PROGRAM.CPP  
```  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [/P (вывод результатов предварительной обработки файла)](../../build/reference/p-preprocess-to-a-file.md)   
 [Указание пути](../../build/reference/specifying-the-pathname.md)