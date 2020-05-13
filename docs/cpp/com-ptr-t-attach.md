---
title: _com_ptr_t::Attach
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::Attach
helpviewer_keywords:
- COM interfaces, attach pointer
- Attach method [C++]
ms.assetid: 94c18e0a-06be-4ca7-bdaf-cd54ec0a645e
ms.openlocfilehash: 057d784bb495aefaeec1b86697a7421f6464cbd7
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81745068"
---
# <a name="_com_ptr_tattach"></a>_com_ptr_t::Attach

**Microsoft Специфический**

Инкапсулирует необработанный указатель на интерфейс для типа этого интеллектуального указателя.

## <a name="syntax"></a>Синтаксис

```cpp
void Attach( Interface* pInterface ) throw( );
void Attach( Interface* pInterface, bool fAddRef ) throw( );
```

#### <a name="parameters"></a>Параметры

*pИнтерфейс*<br/>
Необработанный указатель на интерфейс.

*fAddRef*<br/>
Если это правда, `AddRef` то называется. Если это FALSE, `_com_ptr_t` объект берет на себя ответственность `AddRef`за необработанный указатель интерфейса без вызова.

## <a name="remarks"></a>Remarks

- **Прикрепить (**  *pInterface*  **)** `AddRef` не вызывается. Право на владение интерфейсом передается данному объекту `_com_ptr_t`. `Release`вызывается для decrement отсчета ссылки для ранее инкапсулированного указателя.

- **Прикрепите (***pInterface,* **,***faddRef***)** Если *fAddRef* является `AddRef` правдой, называется для приведения отсчета ссылки на инкапсулированный указатель интерфейса.       Если *fAddRef* является `_com_ptr_t` FALSE, этот объект берет на `AddRef`себя ответственность за необработанный указатель интерфейса без вызова. `Release`вызывается для decrement отсчета ссылки для ранее инкапсулированного указателя.

**END Microsoft Специфический**

## <a name="see-also"></a>См. также раздел

[класс _com_ptr_t](../cpp/com-ptr-t-class.md)
