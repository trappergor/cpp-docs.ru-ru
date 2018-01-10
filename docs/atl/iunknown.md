---
title: "IUnknown | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IUnknown
dev_langs: C++
helpviewer_keywords:
- COM interfaces, base interface
- IUnknown interface
ms.assetid: e6b85472-e54b-4b8c-b19f-4454d6c05a8f
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e46ee55412c591558389bb7ac42116431eaaa6ae
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="iunknown"></a>IUnknown
[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) базовый интерфейс для каждого COM-интерфейса.  Этот интерфейс определяет три метода: [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521), [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), и [выпуска](http://msdn.microsoft.com/library/windows/desktop/ms682317). [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) позволяет пользователю запрашивать указатель на другую из интерфейсов объекта интерфейса. [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) и [выпуска](http://msdn.microsoft.com/library/windows/desktop/ms682317) реализации интерфейса подсчета ссылок.  
  
## <a name="see-also"></a>См. также  
 [Знакомство с COM](../atl/introduction-to-com.md)   
 [IUnknown и наследование интерфейса](http://msdn.microsoft.com/library/windows/desktop/ms692713)

