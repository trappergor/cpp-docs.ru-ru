---
title: "ЗАГЛУШКИ | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- STUB
dev_langs:
- C++
helpviewer_keywords:
- STUB .def file statement
ms.assetid: 0a3b9643-19ed-47e9-8173-ee16bc8ed056
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 58430f8211f8859b65103b53d1f98a173c4635ee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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