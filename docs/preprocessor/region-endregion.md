---
title: Директивы pragma region, endregion
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.endregion
- endregion_CPP
- region_CPP
- vc-pragma.region
helpviewer_keywords:
- pragmas, region
- pragmas, endregion
- endregion pragma
- region pragma
ms.assetid: c697f807-622f-4796-851b-68a42bbecd84
ms.openlocfilehash: 4a01e04582ac81d678aa0702945c62ee974a4428
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222378"
---
# <a name="region-endregion-pragmas"></a>Директивы pragma region, endregion

`#pragma region`позволяет указать блок кода, который можно развернуть или свернуть при использовании [функции структурирования](/visualstudio/ide/outlining) в редакторе Visual Studio Code.

## <a name="syntax"></a>Синтаксис

> **регион #pragma** *имя*\
> **#pragma endregion** *Комментарий*

### <a name="parameters"></a>Параметры

*Метки*\
Используемых Комментарий, отображаемый в редакторе кода.

*безымян*\
Используемых Имя региона. Это имя отображается в редакторе кода.

## <a name="remarks"></a>Примечания

`#pragma endregion`Помечает конец `#pragma region` блока.

Блок должен заканчиваться `#pragma endregion`директивой. `#region`

## <a name="example"></a>Пример

```cpp
// pragma_directives_region.cpp
#pragma region Region_1
void Test() {}
void Test2() {}
void Test3() {}
#pragma endregion Region_1

int main() {}
```

## <a name="see-also"></a>См. также

[Директивы pragma и ключевое слово __pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
