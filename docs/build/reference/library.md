---
title: LIBRARY
ms.date: 11/04/2016
f1_keywords:
- LIBRARY
helpviewer_keywords:
- LIBRARY .def file statement
ms.assetid: 1d7ccc92-e088-4ef7-9ef0-25c3862cc051
ms.openlocfilehash: b43f269726e8925abeefd41aab0edfd57b071035
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62291097"
---
# <a name="library"></a>LIBRARY

Указывает ССЫЛКУ, чтобы создать библиотеку DLL. В то же время ССЫЛКУ создает библиотеку импорта, если только не используется файл EXP в сборке.

```
LIBRARY [library][BASE=address]
```

## <a name="remarks"></a>Примечания

*Библиотеки* аргумент указывает имя библиотеки DLL. Можно также использовать [/OUT](out-output-file-name.md) параметр компоновщика, чтобы указать имя выходной библиотеки DLL.

БАЗОВЫЙ =*адрес* аргумент задает базовый адрес, который операционная система использует для загрузки библиотеки DLL. Этот аргумент переопределяет расположение библиотеки DLL по умолчанию 0x10000000. См. в описании [/BASE](base-base-address.md) подробные сведения о базовых адресов.

Не забывайте использовать [/DLL](dll-build-a-dll.md) параметр компоновщика при построении библиотеки DLL.

## <a name="see-also"></a>См. также

[Правила для операторов определения модуля](rules-for-module-definition-statements.md)
