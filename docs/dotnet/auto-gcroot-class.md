---
title: Класс auto_gcroot
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- msclr::auto_gcroot
- msclr.auto_gcroot
- auto_gcroot
helpviewer_keywords:
- auto_gcroot
ms.assetid: b5790912-265d-463e-a486-47302e91042a
ms.openlocfilehash: cb89035d928b251c9cc0427612ce6853a96456a9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50534242"
---
# <a name="autogcroot-class"></a>Класс auto_gcroot

Управлять ресурсами в автоматическом (таких как [класс auto_ptr](../standard-library/auto-ptr-class.md)) который можно использовать для внедрения виртуальный дескриптор в собственный тип.

## <a name="syntax"></a>Синтаксис

```cpp
template<typename _element_type>
class auto_gcroot;
```

#### <a name="parameters"></a>Параметры

*_element_type*<br/>
Управляемый тип, для внедрения.

## <a name="requirements"></a>Требования

**Файл заголовка** \<msclr\auto_gcroot.h >

**Пространство имен** msclr

## <a name="see-also"></a>См. также

[auto_gcroot](../dotnet/auto-gcroot.md)<br/>
[Члены auto_gcroot](../dotnet/auto-gcroot-members.md)<br/>
[Практическое руководство. Объявление дескрипторов в собственных типах](../dotnet/how-to-declare-handles-in-native-types.md)<br/>
[Класс auto_handle](../dotnet/auto-handle-class.md)