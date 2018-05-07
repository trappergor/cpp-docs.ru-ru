---
title: БИБЛИОТЕКА | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- LIBRARY
dev_langs:
- C++
helpviewer_keywords:
- LIBRARY .def file statement
ms.assetid: 1d7ccc92-e088-4ef7-9ef0-25c3862cc051
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0d2fb7e69b0557bf96601666c390b3d59412b5a0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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