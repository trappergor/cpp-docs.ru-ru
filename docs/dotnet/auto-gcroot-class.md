---
title: Класс auto_gcroot | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- msclr::auto_gcroot
- msclr.auto_gcroot
- auto_gcroot
dev_langs:
- C++
helpviewer_keywords:
- auto_gcroot
ms.assetid: b5790912-265d-463e-a486-47302e91042a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 48412a932ff3752b0613f7045cd88992332b7917
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46423236"
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