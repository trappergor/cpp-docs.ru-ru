---
title: регион, endregion | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 5590d2b251d86a9d20b62bfdb3d5bf929e3d92d4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33839451"
---
# <a name="region-endregion"></a>region, endregion
**#pragma region** позволяет указать блок кода, который можно разворачивать и сворачивать при использовании [функции структурирования](/visualstudio/ide/outlining) редакторе кода Visual Studio.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#pragma region name  
#pragma endregion comment  
```  
  
#### <a name="parameters"></a>Параметры  
 `comment` (необязательно)  
 Комментарий, отображаемый в редакторе кода.  
  
 *имя*(необязательно)  
 Имя области.  Имя, отображаемое в редакторе кода.  
  
## <a name="remarks"></a>Примечания  
 **#pragma endregion** отмечает конец **#pragma region** блока.  
  
 Объект `#region` блок должен заканчиваться **#pragma endregion**.  
  
## <a name="example"></a>Пример  
  
```  
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