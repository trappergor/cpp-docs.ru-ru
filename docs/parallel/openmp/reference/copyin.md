---
title: copyin | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- copyin
dev_langs:
- C++
helpviewer_keywords:
- copyin OpenMP clause
ms.assetid: 369efa88-613c-4cb1-9e11-7b9ee08a4b25
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 27afaee16a87ddf428570f7854212eed34634d38
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46059333"
---
# <a name="copyin"></a>copyin
Позволяет потокам для доступа к значение главного потока для [threadprivate](../../../parallel/openmp/reference/threadprivate.md) переменной.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
copyin(var)  
```  
  
## <a name="parameters"></a>Параметры
  
*var*<br/>
`threadprivate` Переменную, которая будет инициализирован со значением переменной в основной поток, так как она существует до параллельной конструкции.  
  
## <a name="remarks"></a>Примечания  
 `copyin` область применения следующих директив:  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [Разделы](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Дополнительные сведения см. в разделе [2.7.2.7 copyin](../../../parallel/openmp/2-7-2-7-copyin.md).  
  
## <a name="example"></a>Пример  
 См. в разделе [threadprivate](../../../parallel/openmp/reference/threadprivate.md) пример использования `copyin`.  
  
## <a name="see-also"></a>См. также  
 [Предложения](../../../parallel/openmp/reference/openmp-clauses.md)