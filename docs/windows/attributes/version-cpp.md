---
title: версия (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.version
helpviewer_keywords:
- version attribute
- version information, version attribute
ms.assetid: db6ce5d8-82c2-4329-b1a8-8ca2f67342cb
ms.openlocfilehash: b537f56c39c33abc52897cf53ea2cc0fb24ee458
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213805"
---
# <a name="version-c"></a>version (C++)

Определяет определенную версию для нескольких версий класса.

## <a name="syntax"></a>Синтаксис

```cpp
[ version("version") ]
```

### <a name="parameters"></a>Параметры

*version*<br/>
Номер версии `coclass`. Если не указано, 1,0 будет помещена в IDL-файл.

## <a name="remarks"></a>Remarks

Атрибут **Version** C++ имеет те же функциональные возможности, что и атрибут MIDL [версии](/windows/win32/Midl/version) , и передается в созданный IDL-файл.

## <a name="example"></a>Пример

Пример использования **версии**см. в примере с [возможностью привязки](bindable.md) .

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Относится к**|**`class`**, **`struct`**|
|**REPEATABLE**|Нет|
|**Требуемые атрибуты**|**кокласс**|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты компилятора](compiler-attributes.md)<br/>
[Атрибуты класса](class-attributes.md)
