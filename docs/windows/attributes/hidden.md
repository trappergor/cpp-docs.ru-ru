---
title: Hidden (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.hidden
helpviewer_keywords:
- hidden attribute
ms.assetid: 199c96dd-fc07-46c7-af93-92020aebebe7
ms.openlocfilehash: 6b420e8f50bd217de460a81f5faaf9583c701376
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80168100"
---
# <a name="hidden"></a>hidden

Указывает, что элемент существует, но не должен отображаться в браузере, ориентированном на пользователя.

## <a name="syntax"></a>Синтаксис

```cpp
[hidden]
```

## <a name="remarks"></a>Remarks

Атрибут **Hidden** C++ имеет те же функциональные возможности, что и [скрытый](/windows/win32/Midl/hidden) атрибут MIDL.

## <a name="example"></a>Пример

См. пример для [привязки](bindable.md) к примеру, как использовать **скрытый**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**интерфейс**, **класс**, **Структура**, метод, свойство|
|**Повторяемый**|нет|
|**Обязательные атрибуты**|**coclass** (при применении к **классу** или **структуре**)|
|**Недопустимые атрибуты**|None|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты интерфейса](interface-attributes.md)<br/>
[Атрибуты классов](class-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)
