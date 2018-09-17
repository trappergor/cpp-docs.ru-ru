---
title: БИБЛИОТЕКА | Документация Майкрософт
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
ms.openlocfilehash: 43b14e8e8ff4871ba4319c7f4fac5545e72e710b
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45723558"
---
# <a name="library"></a>LIBRARY

Указывает ССЫЛКУ, чтобы создать библиотеку DLL. В то же время ССЫЛКУ создает библиотеку импорта, если только не используется файл EXP в сборке.

```
LIBRARY [library][BASE=address]
```

## <a name="remarks"></a>Примечания

*Библиотеки* аргумент указывает имя библиотеки DLL. Можно также использовать [/OUT](../../build/reference/out-output-file-name.md) параметр компоновщика, чтобы указать имя выходной библиотеки DLL.

БАЗОВЫЙ =*адрес* аргумент задает базовый адрес, который операционная система использует для загрузки библиотеки DLL. Этот аргумент переопределяет расположение библиотеки DLL по умолчанию 0x10000000. См. в описании [/BASE](../../build/reference/base-base-address.md) подробные сведения о базовых адресов.

Не забывайте использовать [/DLL](../../build/reference/dll-build-a-dll.md) параметр компоновщика при построении библиотеки DLL.

## <a name="see-also"></a>См. также

[Правила для операторов определения модуля](../../build/reference/rules-for-module-definition-statements.md)