---
title: версия (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.version
helpviewer_keywords:
- version attribute
- version information, version attribute
ms.assetid: db6ce5d8-82c2-4329-b1a8-8ca2f67342cb
ms.openlocfilehash: 9a432267632b1f2a716a833a485b182cd93a27e2
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514874"
---
# <a name="version-c"></a>version (C++)

Определяет определенную версию для нескольких версий класса.

## <a name="syntax"></a>Синтаксис

```cpp
[ version("version") ]
```

### <a name="parameters"></a>Параметры

*version*<br/>
Номер `coclass`версии. Если не указано, 1,0 будет помещена в IDL-файл.

## <a name="remarks"></a>Примечания

Атрибут **Version** C++ имеет те же функциональные возможности, что и атрибут MIDL [версии](/windows/win32/Midl/version) , и передается в созданный IDL-файл.

## <a name="example"></a>Пример

Пример использования **версии**см. в примере с [возможностью привязки](bindable.md) .

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Относится к**|**класс**, **Структура**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|**кокласс**|
|**Недопустимые атрибуты**|Отсутствуют|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты компилятора](compiler-attributes.md)<br/>
[Атрибуты классов](class-attributes.md)