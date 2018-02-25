---
title: "оператор== (&lt;образец контейнера&gt;) | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- std.==
- std::==
- operator==
- std.operator==
- std::operator==
- ==
dev_langs:
- C++
helpviewer_keywords:
- operator ==, containers
- operator==, containers
- == operator, with specific standard C++ objects
ms.assetid: d3d8754e-5157-4b8b-bf9c-da41856f5eed
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 43fe92355367d03a23b2540c79dcda4562a5df15
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="operator-ltsample-containergt"></a>оператор== (&lt;образец контейнера&gt;)
> [!NOTE]
>  Данный раздел включен в документацию Visual C++ в качестве нефункционального примера контейнеров, используемых в стандартной библиотеке C++. Дополнительные сведения см. в разделе [Контейнеры стандартной библиотеки C++](../standard-library/stl-containers.md).  
  
 Перегружает `operator==` для сравнения двух объектов класса шаблона [контейнер](../standard-library/sample-container-class.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <class Ty>  
bool operator==(
    const Container <Ty>& left,  
    const Container <Ty>& right);
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает `left.` [размер](../standard-library/container-class-size.md) ` == right.size && equal(left.` [начать](../standard-library/container-class-begin.md)`, left.`[окончания](../standard-library/container-class-end.md)`, right.begin)`.  
  
## <a name="see-also"></a>См. также  
 [\<образец контейнера>](../standard-library/sample-container.md)

