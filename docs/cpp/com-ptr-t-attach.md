---
title: _com_ptr_t::Attach
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::Attach
helpviewer_keywords:
- COM interfaces, attach pointer
- Attach method [C++]
ms.assetid: 94c18e0a-06be-4ca7-bdaf-cd54ec0a645e
ms.openlocfilehash: 870e3580ed23ce994d832f7c59b951680d725e41
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180502"
---
# <a name="_com_ptr_tattach"></a>_com_ptr_t::Attach

**Блок, относящийся только к системам Microsoft**

Инкапсулирует необработанный указатель на интерфейс для типа этого интеллектуального указателя.

## <a name="syntax"></a>Синтаксис

```
void Attach( Interface* pInterface ) throw( );
void Attach( Interface* pInterface, bool fAddRef ) throw( );
```

#### <a name="parameters"></a>Параметры

*пинтерфаце*<br/>
Необработанный указатель на интерфейс.

*фаддреф*<br/>
Если это так, то вызывается `AddRef`. Если он имеет значение FALSE, то объект `_com_ptr_t` берет на себя владение указателем необработанного интерфейса без вызова `AddRef`.

## <a name="remarks"></a>Remarks

- **Присоединение (**  *пинтерфаце*  **)** `AddRef` не вызывается. Право на владение интерфейсом передается данному объекту `_com_ptr_t`. `Release` вызывается для уменьшения счетчика ссылок для ранее инкапсулированного указателя.

- **Attach (**  *пинтерфаце* **,**  *фаддреф*  **)** Если *фаддреф* имеет значение true, вызывается `AddRef`, чтобы увеличить число ссылок для указателя инкапсулированного интерфейса. Если *фаддреф* имеет значение false, то этот объект `_com_ptr_t` получает владение указателем необработанного интерфейса без вызова `AddRef`. `Release` вызывается для уменьшения счетчика ссылок для ранее инкапсулированного указателя.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[Класс _com_ptr_t](../cpp/com-ptr-t-class.md)
