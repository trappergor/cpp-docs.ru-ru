---
title: Hidden (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.hidden
helpviewer_keywords:
- hidden attribute
ms.assetid: 199c96dd-fc07-46c7-af93-92020aebebe7
ms.openlocfilehash: 75b03877b1204d6e1c4770f5ba9c8c88338b3394
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69501451"
---
# <a name="hidden"></a>hidden

Указывает, что элемент существует, но не должен отображаться в браузере, ориентированном на пользователя.

## <a name="syntax"></a>Синтаксис

```cpp
[hidden]
```

## <a name="remarks"></a>Примечания

Атрибут **Hidden** C++ имеет те же функциональные возможности, что и [скрытый](/windows/win32/Midl/hidden) атрибут MIDL.

## <a name="example"></a>Пример

См. пример для [привязки](bindable.md) к примеру, как использовать **скрытый**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Относится к**|**интерфейс**, **класс**, **Структура**, метод, свойство|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|**coclass** (при применении к **классу** или **структуре**)|
|**Недопустимые атрибуты**|Отсутствуют|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты интерфейса](interface-attributes.md)<br/>
[Атрибуты классов](class-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)