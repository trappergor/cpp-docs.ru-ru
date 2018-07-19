---
title: IUnknown | Документация Майкрософт
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
ms.openlocfilehash: d832d2978bf9db82b290d77b236fea1c9bcada58
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38953046"
---
# <a name="iunknown"></a>IUnknown
[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) является базовым интерфейсом каждого второго COM-интерфейса.  Этот интерфейс определяет три метода: [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521), [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), и [выпуска](http://msdn.microsoft.com/library/windows/desktop/ms682317). [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) позволяет пользователю интерфейса запрашивать указатель на другой интерфейс объекта. [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) и [выпуска](http://msdn.microsoft.com/library/windows/desktop/ms682317) реализуют подсчет ссылок в интерфейсе.  
  
## <a name="see-also"></a>См. также  
 [Введение в модель COM](../atl/introduction-to-com.md)   
 [IUnknown и наследование интерфейса](http://msdn.microsoft.com/library/windows/desktop/ms692713)

