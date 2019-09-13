---
title: high_method_prefix, атрибут импорта
ms.date: 08/29/2019
f1_keywords:
- high_method_prefix
helpviewer_keywords:
- high_method_prefix attribute
ms.assetid: cacebf09-12f5-4919-ad40-939e206e340c
ms.openlocfilehash: 357ac528a921a9f864f0f7e30252281a4d10e33c
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219020"
---
# <a name="high_method_prefix-import-attribute"></a>high_method_prefix, атрибут импорта

**C++Зависящ**

Задает префикс, используемый при именовании высокоуровневых свойств и методов.

## <a name="syntax"></a>Синтаксис

> **#import** *Библиотека типов* **high_method_prefix (** "*префикс*" **)**

### <a name="parameters"></a>Параметры

*Prefix*\
Префикс, который следует использовать.

## <a name="remarks"></a>Примечания

По умолчанию высокоуровневые свойства и методы обработки ошибок предоставляются функциями-членами с именами без префикса. Это имена из библиотеки типов.

**КОНЕЦ C++ конкретного**

## <a name="see-also"></a>См. также

[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)\
[Директива #import](../preprocessor/hash-import-directive-cpp.md)
