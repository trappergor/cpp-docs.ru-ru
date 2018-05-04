---
title: ЗАГЛУШКИ | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- STUB
dev_langs:
- C++
helpviewer_keywords:
- STUB .def file statement
ms.assetid: 0a3b9643-19ed-47e9-8173-ee16bc8ed056
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 385e073f877a938a3b73fa79036d27cf50c1e4ec
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="stub"></a>STUB
При использовании в файл определения модуля, который создает драйверов виртуальных устройств (VxD), можно указать имя файла, который содержит структуру IMAGE_DOS_HEADER (определенную в файле WINNT. (H) для использования в драйверов виртуальных устройств (VxD), а не заголовок по умолчанию.  
  
```  
STUB:filename  
```  
  
## <a name="remarks"></a>Примечания  
 Можно указать *filename* с [/STUB](../../build/reference/stub-ms-dos-stub-file-name.md) компоновщика.  
  
 ЗАГЛУШКИ является допустимым в файл определения модуля только при построении VxD.  
  
## <a name="see-also"></a>См. также  
 [Правила для операторов определения модуля](../../build/reference/rules-for-module-definition-statements.md)