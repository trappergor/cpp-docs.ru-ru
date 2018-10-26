---
title: Спецификаторы переопределения (C + +/ CLI и C + +/ CX) | Документация Майкрософт
ms.custom: ''
ms.date: 10/12/2018
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- override specifiers, C++
- override specifiers
ms.assetid: 155bbf6f-4722-4654-afb1-9cb52af799fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0620bc7045dcb312667cfdfe670e1f19b0545cf2
ms.sourcegitcommit: 3f4e92266737ecb70507871e87dc8e2965ad7e04
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2018
ms.locfileid: "49327468"
---
# <a name="override-specifiers--ccli-and-ccx"></a>Спецификаторы переопределения (C + +/ CLI и C + +/ CX)

*Спецификаторы переопределения* изменяют поведение унаследованных типов и членов унаследованных типов ведут себя в производных типах.

## <a name="all-runtimes"></a>Все среды выполнения

### <a name="remarks"></a>Примечания

Дополнительные сведения о спецификаторах переопределения см. в разделах:

- [abstract](../windows/abstract-cpp-component-extensions.md)

- [New (новый слот в vtable)](../windows/new-new-slot-in-vtable-cpp-component-extensions.md)

- [override](../windows/override-cpp-component-extensions.md)

- [sealed](../windows/sealed-cpp-component-extensions.md)

- [Спецификаторы переопределения и компиляции в машинный код](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md)

**Абстрактный** и **запечатанный** относятся также и на объявления типа, где они не действуют как спецификаторы переопределения.

Сведения о явного переопределения функции базового класса, см. в разделе [явное переопределение](../windows/explicit-overrides-cpp-component-extensions.md).

## <a name="windows-runtime"></a>Среда выполнения Windows

(Отсутствуют комментарии для этой возможности языка, которая применяется только в среде выполнения Windows).

### <a name="requirements"></a>Требования

Параметр компилятора: `/ZW`

## <a name="common-language-runtime"></a>Среда CLR

(Отсутствуют комментарии для этой функции языка, которая применяется только в среде CLR).

### <a name="requirements"></a>Требования

Параметр компилятора: `/clr`

## <a name="see-also"></a>См. также

[Расширения компонентов для .NET и универсальной платформы Windows](../windows/component-extensions-for-runtime-platforms.md)