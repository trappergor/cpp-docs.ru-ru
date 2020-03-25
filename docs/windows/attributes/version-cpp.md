---
title: версия (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.version
helpviewer_keywords:
- version attribute
- version information, version attribute
ms.assetid: db6ce5d8-82c2-4329-b1a8-8ca2f67342cb
ms.openlocfilehash: e5fcf80ef753a869b8798d6ab9c8e9f8ecff16fd
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165994"
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
|**Применение**|**класс**, **Структура**|
|**Повторяемый**|нет|
|**Обязательные атрибуты**|**кокласс**|
|**Недопустимые атрибуты**|None|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты компилятора](compiler-attributes.md)<br/>
[Атрибуты классов](class-attributes.md)
