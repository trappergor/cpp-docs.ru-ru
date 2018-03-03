---
title: "БИБЛИОТЕКА | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- LIBRARY
dev_langs:
- C++
helpviewer_keywords:
- LIBRARY .def file statement
ms.assetid: 1d7ccc92-e088-4ef7-9ef0-25c3862cc051
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 71637c83eda0ee641a4b66d94ba113162baa7bf2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="library"></a>LIBRARY
Указывает ССЫЛКУ, чтобы создать библиотеку DLL. В то же время LINK создает библиотеку импорта, если только не используется файл EXP в сборке.  
  
```  
LIBRARY [library][BASE=address]  
```  
  
## <a name="remarks"></a>Примечания  
 *Библиотеки* аргумент задает имя библиотеки DLL. Можно также использовать [/OUT](../../build/reference/out-output-file-name.md) компоновщика, чтобы указать имя выходной библиотеки DLL.  
  
 БАЗОВЫЙ =*адрес* аргумент задает базовый адрес, который операционная система использует для загрузки библиотеки DLL. Этот аргумент переопределяет расположение библиотеки DLL по умолчанию 0x10000000. См. в описании [/BASE](../../build/reference/base-base-address.md) подробные сведения о базовых адресов.  
  
 Не забывайте использовать [/DLL](../../build/reference/dll-build-a-dll.md) компоновщика при построении библиотеки DLL.  
  
## <a name="see-also"></a>См. также  
 [Правила для операторов определения модуля](../../build/reference/rules-for-module-definition-statements.md)