---
title: _com_ptr_t::Attach
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::Attach
helpviewer_keywords:
- COM interfaces, attach pointer
- Attach method [C++]
ms.assetid: 94c18e0a-06be-4ca7-bdaf-cd54ec0a645e
ms.openlocfilehash: 4b4b7a21d12cc645c486dd93d555510c1e716563
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50566547"
---
# <a name="comptrtattach"></a>_com_ptr_t::Attach

**Блок, относящийся только к системам Microsoft**

Инкапсулирует необработанный указатель на интерфейс для типа этого интеллектуального указателя.

## <a name="syntax"></a>Синтаксис

```
void Attach( Interface* pInterface ) throw( );
void Attach( Interface* pInterface, bool fAddRef ) throw( );
```

#### <a name="parameters"></a>Параметры

*pInterface*<br/>
Необработанный указатель на интерфейс.

*fAddRef*<br/>
Если он имеет значение TRUE, затем `AddRef` вызывается. Если он имеет значение FALSE, `_com_ptr_t` объект принимает владение базовым указателем на интерфейс без вызова `AddRef`.

## <a name="remarks"></a>Примечания

- **Присоединение (***pInterface***)** `AddRef` не вызывается. Право на владение интерфейсом передается данному объекту `_com_ptr_t`. `Release` вызывается для уменьшения счетчика ссылок для ранее инкапсулированного указателя.

- **Присоединение (***pInterface* **,***fAddRef***)** Если *fAddRef* имеет значение TRUE, `AddRef`вызывается следует выполнить приращение счетчика ссылок для указателя инкапсулированного интерфейса. Если *fAddRef* имеет значение FALSE, это `_com_ptr_t` объект принимает владение базовым указателем на интерфейс без вызова `AddRef`. `Release` вызывается для уменьшения счетчика ссылок для ранее инкапсулированного указателя.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Класс _com_ptr_t](../cpp/com-ptr-t-class.md)