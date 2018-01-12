---
title: "-Fi (Предварительная обработка имени выходного файла) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /Fi
dev_langs: C++
helpviewer_keywords:
- Fi compiler option (C++)
- -Fi compiler option (C++)
- /Fi compiler option (C++)
- preprocessing output files, file name
ms.assetid: 6d0ba983-a8b7-41ec-84f5-b4688ef8efee
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9bc3076a529984358aed16902f509ceb01423f9e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="fi-preprocess-output-file-name"></a>/Fi (предварительная обработка имени выходного файла)
Задает имя выходного файла, к которому [/P (Предварительная обработка в файл)](../../build/reference/p-preprocess-to-a-file.md) параметр компилятора записывает предварительно обработанные выходные данные.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/Fipathname  
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание:|  
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