---
title: регион, endregion | Документация Майкрософт
ms.custom: ''
ms.date: 10/18/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.endregion
- endregion_CPP
- region_CPP
- vc-pragma.region
dev_langs:
- C++
helpviewer_keywords:
- pragmas, region
- pragmas, endregion
- endregion pragma
- region pragma
ms.assetid: c697f807-622f-4796-851b-68a42bbecd84
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2e360009eb9126604d4466daed2445c7dfc582d4
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49808073"
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