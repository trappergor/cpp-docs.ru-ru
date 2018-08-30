---
title: версия (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.version
dev_langs:
- C++
helpviewer_keywords:
- version attribute
- version information, version attribute
ms.assetid: db6ce5d8-82c2-4329-b1a8-8ca2f67342cb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 87186ee70b5863f51a7cd91f8695052f361bd11c
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43222536"
---
# <a name="version-c"></a>version (C++)

Идентифицирует конкретную версию несколькими версиями класса.

## <a name="syntax"></a>Синтаксис

```cpp
[ version(
   "version"
) ]
```

### <a name="parameters"></a>Параметры

*version*  
Номер версии `coclass`. Если не указан, 1.0 помещаются в IDL-файл.

## <a name="remarks"></a>Примечания

**Версии** атрибут C++ имеет ту же функциональность, что [версии](/windows/desktop/Midl/version) описании атрибута MIDL и передается через созданного IDL-файла.

## <a name="example"></a>Пример

См. в разделе [bindable](../windows/bindable.md) пример для использовать **версии**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**Класс**, **структуры**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|**coclass**|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).

## <a name="see-also"></a>См. также

[Атрибуты компилятора](../windows/compiler-attributes.md)  
[Атрибуты классов](../windows/class-attributes.md)  