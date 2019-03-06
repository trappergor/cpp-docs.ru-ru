---
title: LIBRARY
ms.date: 11/04/2016
f1_keywords:
- LIBRARY
helpviewer_keywords:
- LIBRARY .def file statement
ms.assetid: 1d7ccc92-e088-4ef7-9ef0-25c3862cc051
ms.openlocfilehash: 73609be698719da05fff357ba80200c49f598add
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57422676"
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
