---
title: raw_interfaces_only, атрибут импорта
ms.date: 08/29/2019
f1_keywords:
- raw_interfaces_only
helpviewer_keywords:
- raw_interfaces_only attribute
ms.assetid: 87056c6d-3f34-4248-af58-f5775a35bfb7
ms.openlocfilehash: 4b79aa4dbafa204d84f4d6ed7ec78fdec1b81fa7
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216204"
---
# <a name="raw_interfaces_only-import-attribute"></a>raw_interfaces_only, атрибут импорта

**C++Зависящ**

Подавляет создание функций-оболочек обработки ошибок и объявлений [свойств](../cpp/property-cpp.md) , использующих эти функции-оболочки.

## <a name="syntax"></a>Синтаксис

> **#import** *Библиотека типов* **raw_interfaces_only**

## <a name="remarks"></a>Примечания

Атрибут **raw_interfaces_only** также вызывает префикс по умолчанию, используемый при именовании удаляемых функций, не являющихся свойствами. Как правило, префикс имеет `raw_`значение. Если этот атрибут указан, имена функций берутся непосредственно из библиотеки типов.

Этот атрибут позволяет предоставлять только низкоуровневое содержимое библиотеки типов.

**КОНЕЦ C++ конкретного**

## <a name="see-also"></a>См. также

[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)\
[Директива #import](../preprocessor/hash-import-directive-cpp.md)
