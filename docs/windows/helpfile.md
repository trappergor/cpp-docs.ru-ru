---
title: HelpFile | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.helpfile
dev_langs:
- C++
helpviewer_keywords:
- helpfile attribute
ms.assetid: d75161c1-1363-4019-ae09-e7e3b8a3971e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 424c6b642bba04a22ee4dedd59e38761260ac8eb
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43221933"
---
# <a name="helpfile"></a>helpfile

Задает имя файла справки для библиотеки типов.

## <a name="syntax"></a>Синтаксис

```cpp
[ helpfile(
   "filename"
) ]
```

### <a name="parameters"></a>Параметры

*filename*  
Имя файла, который содержит разделы справки.

## <a name="remarks"></a>Примечания

**Helpfile** атрибут C++ имеет ту же функциональность, что [helpfile](/windows/desktop/Midl/helpfile) описании атрибута MIDL.

## <a name="example"></a>Пример

См. в примере [модуль](../windows/module-cpp.md) пример демонстрирует использование **helpfile**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**интерфейс**, **typedef**, **класс**, метод, **свойство**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).

## <a name="see-also"></a>См. также

[Атрибуты IDL](../windows/idl-attributes.md)  
[Атрибуты интерфейса](../windows/interface-attributes.md)  
[Атрибуты классов](../windows/class-attributes.md)  
[Атрибуты метода](../windows/method-attributes.md)  
[Атрибуты Typedef, Enum, Union и Struct](../windows/typedef-enum-union-and-struct-attributes.md)  
[helpcontext](../windows/helpcontext.md)  
[helpstring](../windows/helpstring.md)  