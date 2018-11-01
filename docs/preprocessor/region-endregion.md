---
title: region, endregion
ms.date: 10/18/2018
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
ms.openlocfilehash: efc5f9c09449ff2fefff41261fe8b0eb0be80278
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512818"
---
# <a name="region-endregion"></a>region, endregion

`#pragma region` позволяет указать блок кода, который можно разворачивать и сворачивать с помощью [возможности структурирования](/visualstudio/ide/outlining) редактор кода Visual Studio.

## <a name="syntax"></a>Синтаксис

```
#pragma region name
#pragma endregion comment
```

### <a name="parameters"></a>Параметры

*comment*<br/>
(Необязательно) Комментарий, который будет отображаться в редакторе кода.

*name*<br/>
(Необязательно) Имя области.  Имя, отображаемое в редакторе кода.

## <a name="remarks"></a>Примечания

`#pragma endregion` Помечает конец `#pragma region` блока.

Объект `#region` блок должен заканчиваться `#pragma endregion`.

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

[Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)