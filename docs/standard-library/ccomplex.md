---
title: '&lt;ccomplex&gt; | Документы Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <ccomplex>
dev_langs:
- C++
ms.assetid: a9fcb5f0-88e3-464b-a5fd-d1afb8cd7e6f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: de5c67fc88da6fc4674b7dad67b5f74dcc3ce54d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33850389"
---
# <a name="ltccomplexgt"></a>&lt;ccomplex&gt;

Включает заголовок стандартной библиотеки C++ [\<complex>](../standard-library/complex.md), который эффективно включает заголовок \<complex.h> стандартной библиотеки C и добавляет связанные имена в пространство имен `std`.

## <a name="syntax"></a>Синтаксис

```cpp
#include <ccomplex>

```

## <a name="remarks"></a>Примечания

Включение этого заголовка гарантирует, что имена, объявленные с помощью внешней компоновки в заголовке стандартной библиотеки C, объявляются в пространстве имен `std`.

Имя `clog`, которое объявлено в \<complex.h>, не определено в пространстве имен `std` из-за возможных конфликтов с `clog`, объявленным в [\<iostream>](../standard-library/iostream.md).

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[Общие сведения о стандартной библиотеке C++](../standard-library/cpp-standard-library-overview.md)<br/>
