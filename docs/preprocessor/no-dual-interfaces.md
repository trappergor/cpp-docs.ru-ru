---
title: no_dual_interfaces, атрибут импорта
ms.date: 08/29/2019
f1_keywords:
- no_dual_interfaces
helpviewer_keywords:
- no_dual_interfaces attribute
ms.assetid: 9acd5d9d-4a49-4cdc-9470-73a2c23cf512
ms.openlocfilehash: 6270888f0d31e4fbe18fb3364995be8c73426b83
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220766"
---
# <a name="no_dual_interfaces-import-attribute"></a>no_dual_interfaces, атрибут импорта

**C++Зависящ**

Изменяет способ, которым компилятор создает функции оболочки для методов сдвоенных интерфейсов.

## <a name="syntax"></a>Синтаксис

> **#import** *Библиотека типов* **no_dual_interfaces**

## <a name="remarks"></a>Примечания

Как правило, обертка вызывает метод через таблицу виртуальной функции для интерфейса. При использовании **no_dual_interfaces**оболочка вместо этого `IDispatch::Invoke` вызывает метод для вызова метода.

**КОНЕЦ C++ конкретного**

## <a name="see-also"></a>См. также

[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)\
[Директива #import](../preprocessor/hash-import-directive-cpp.md)
