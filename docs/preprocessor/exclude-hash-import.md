---
title: исключить атрибут импорта
ms.date: 08/29/2019
f1_keywords:
- exclude
helpviewer_keywords:
- exclude attribute
ms.assetid: 0883248a-d4bf-420e-9848-807b28fa976e
ms.openlocfilehash: 6a3625ee0dd44f3e2731e1240fea5f3dd4ed109e
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218718"
---
# <a name="exclude-import-attribute"></a>исключить атрибут импорта

**C++Зависящ**

Исключает элементы из создаваемых файлов заголовка библиотеки типов.

## <a name="syntax"></a>Синтаксис

> **#import** *Библиотека типов* **Exclude (** "*name1*" [ **,** "*имя2*"...] **)**

### <a name="parameters"></a>Параметры

*Name1*\
Первый исключаемый элемент.

*Name2*\
Используемых Второй и более поздние элементы, которые необходимо исключить при необходимости.

## <a name="remarks"></a>Примечания

Библиотеки типов могут содержать определения элементов, которые определены в системных заголовочных файлах или других библиотеках типов. Этот атрибут может принимать любое количество аргументов, где каждый представляет собой элемент библиотеки типов верхнего уровня, который должен быть исключен.

**КОНЕЦ C++ конкретного**

## <a name="see-also"></a>См. также

[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)\
[Директива #import](../preprocessor/hash-import-directive-cpp.md)
