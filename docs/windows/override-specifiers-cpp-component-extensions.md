---
title: Спецификаторы переопределения (C + +/ CLI и C + +/ CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- override specifiers, C++
- override specifiers
ms.assetid: 155bbf6f-4722-4654-afb1-9cb52af799fb
ms.openlocfilehash: 9d839b9530cff144cda7897b0c96af48c14454a6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50639860"
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

[Расширения компонентов для .NET и UWP](../windows/component-extensions-for-runtime-platforms.md)