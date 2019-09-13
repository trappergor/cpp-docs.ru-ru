---
title: IUnknown
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- COM interfaces, base interface
- IUnknown interface
ms.assetid: e6b85472-e54b-4b8c-b19f-4454d6c05a8f
ms.openlocfilehash: 9c9faa4cffcdc8e6840dfbbe141cb63f51155ded
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492069"
---
# <a name="iunknown"></a>IUnknown

[IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) является базовым интерфейсом для каждого другого COM-интерфейса.  Этот интерфейс определяет три метода: [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)), [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref)и [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release). [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) позволяет пользователю интерфейса запрашивать у объекта указатель на другой интерфейс. [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref) и [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release) реализуют подсчет ссылок на интерфейсе.

## <a name="see-also"></a>См. также

[Введение в модель COM](../atl/introduction-to-com.md)<br/>
[IUnknown и наследование интерфейсов](/windows/win32/com/iunknown-and-interface-inheritance)
