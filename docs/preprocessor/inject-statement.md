---
title: inject_statement, атрибут импорта
ms.date: 08/29/2019
f1_keywords:
- inject_statement
helpviewer_keywords:
- inject_statement attribute
ms.assetid: 07d6f0f4-d9fb-4e18-aa62-f235f142ff5e
ms.openlocfilehash: 25dee621ff8af2c9a39e605b9da2c29d80f9570a
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220990"
---
# <a name="inject_statement-import-attribute"></a>inject_statement, атрибут импорта

**C++Зависящ**

Вставляет свой аргумент как исходный текст в заголовок библиотеки типов.

## <a name="syntax"></a>Синтаксис

> **#import** *Библиотека типов* **inject_statement (** "*Исходный текст*" **)**

### <a name="parameters"></a>Параметры

*исходный текст*\
Исходный текст, вставляемый в файл заголовка библиотеки типов.

## <a name="remarks"></a>Примечания

Текст помещается в начало объявления пространства имен, которое служит оболочкой для содержимого *библиотеки типов* в файле заголовка.

**КОНЕЦ C++ конкретного**

## <a name="see-also"></a>См. также

[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)\
[Директива #import](../preprocessor/hash-import-directive-cpp.md)
