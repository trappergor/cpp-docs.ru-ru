---
title: IUnknown | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IUnknown
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, base interface
- IUnknown interface
ms.assetid: e6b85472-e54b-4b8c-b19f-4454d6c05a8f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c02018ee3cefb1b98c2df850d44578cf3a092c64
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="iunknown"></a>IUnknown
[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) базовый интерфейс для каждого COM-интерфейса.  Этот интерфейс определяет три метода: [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521), [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), и [выпуска](http://msdn.microsoft.com/library/windows/desktop/ms682317). [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) позволяет пользователю запрашивать указатель на другую из интерфейсов объекта интерфейса. [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) и [выпуска](http://msdn.microsoft.com/library/windows/desktop/ms682317) реализации интерфейса подсчета ссылок.  
  
## <a name="see-also"></a>См. также  
 [Знакомство с COM](../atl/introduction-to-com.md)   
 [IUnknown и наследование интерфейса](http://msdn.microsoft.com/library/windows/desktop/ms692713)

