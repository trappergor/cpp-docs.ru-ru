---
title: Метод WeakReference::SetUnknown | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::WeakReference::SetUnknown
dev_langs:
- C++
helpviewer_keywords:
- SetUnknown method
ms.assetid: 5dddb9e3-a7c1-4195-8166-97c5ab6e972f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6fc7accbad5633bd57d7fceb16f82edb82d80f4e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46422497"
---
# <a name="weakreferencesetunknown-method"></a>Метод WeakReference::SetUnknown

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
void SetUnknown(
   _In_ IUnknown* unk
);
```

### <a name="parameters"></a>Параметры

*UNK*<br/>
Указатель на `IUnknown` интерфейс для объекта.

## <a name="remarks"></a>Примечания

Задает строгая ссылка текущего **WeakReference** объект в заданный указатель интерфейса.

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="see-also"></a>См. также

[Класс WeakReference](../windows/weakreference-class1.md)<br/>
[Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)