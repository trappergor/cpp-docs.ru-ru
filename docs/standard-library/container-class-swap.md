---
title: "Класс контейнера::swap | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: swap method
ms.assetid: 898c219c-bc8e-4d14-a149-6240426c693f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 09229429c64e895a722d52d203f0259cf69e6d24
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="container-classswap"></a>Класс контейнера::swap
> [!NOTE]
>  Данный раздел включен в документацию Visual C++ в качестве нефункционального примера контейнеров, используемых в стандартной библиотеке C++. Дополнительные сведения см. в разделе [Контейнеры стандартной библиотеки C++](../standard-library/stl-containers.md).  
  
Меняет местами управляемые последовательности между **\*this**.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void swap(Container& right);
```  
  
## <a name="remarks"></a>Примечания  
Если **\*this.get\_allocator ==** _right_**.get_allocator**, перестановка выполняется в постоянном времени. В противном случае она выполняет ряд назначений элементов и вызовов конструктора, пропорционально количеству элементов в двух управляемых последовательностях.  
  
## <a name="see-also"></a>См. также  
[Пример класса контейнера](../standard-library/sample-container-class.md)
