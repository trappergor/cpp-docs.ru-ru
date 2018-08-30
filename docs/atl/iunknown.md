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
ms.openlocfilehash: acabc38b115429c88ac9bed0e509cbcadd78a5aa
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43217500"
---
# <a name="iunknown"></a>IUnknown
[IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) является базовым интерфейсом каждого второго COM-интерфейса.  Этот интерфейс определяет три метода: [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)), [AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref), и [выпуска](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release). [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) позволяет пользователю интерфейса запрашивать указатель на другой интерфейс объекта. [AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref) и [выпуска](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release) реализуют подсчет ссылок в интерфейсе.  
  
## <a name="see-also"></a>См. также  
 [Введение в модель COM](../atl/introduction-to-com.md)   
 [IUnknown и наследование интерфейса](/windows/desktop/com/iunknown-and-interface-inheritance)

