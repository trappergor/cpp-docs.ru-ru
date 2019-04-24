---
title: include()
ms.date: 10/18/2018
f1_keywords:
- include()
helpviewer_keywords:
- include() attribute
ms.assetid: 86c9dcb2-d9e0-4fd5-97d7-0bb3e23d6ecc
ms.openlocfilehash: 1208f14a9f6b3724dd5353df57213baa3910d07f
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59040931"
---
# <a name="include"></a>include()

**Конкретных C++**

Отключает автоматическое исключение.

## <a name="syntax"></a>Синтаксис

```
include("Name1"[,"Name2", ...])
```

### <a name="parameters"></a>Параметры

*Name1*<br/>
Первый элемент для принудительного включения.

*Имя 2*<br/>
Второй элемент для принудительного включения (при необходимости).

## <a name="remarks"></a>Примечания

Библиотеки типов могут содержать определения элементов, которые определены в системных заголовочных файлах или других библиотеках типов. Директива `#import` пытается предотвратить ошибки об использовании нескольких определений, автоматически исключая такие элементы. Если элементы были исключены, обозначенный [Предупреждение компилятора (уровень 3) C4192](../error-messages/compiler-warnings/compiler-warning-level-3-c4192.md), и они не должны были, этот атрибут может использоваться для отключения автоматического исключения. Этот атрибут может принимать любое количество аргументов, каждый из которых является именем включаемого элемента библиотеки типов.

**КОНЕЦ конкретных C++**

## <a name="see-also"></a>См. также

[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)<br/>
[директива #import](../preprocessor/hash-import-directive-cpp.md)