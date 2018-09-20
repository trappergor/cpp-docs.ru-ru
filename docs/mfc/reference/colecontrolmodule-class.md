---
title: Класс COleControlModule | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- OleControlModule
dev_langs:
- C++
helpviewer_keywords:
- OLE control modules [MFC]
- MFC ActiveX controls [MFC], OLE control modules
- COleControlModule class [MFC]
- control modules [MFC]
ms.assetid: 0721724d-d4af-4eda-ad34-5a2b27810dd4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8139f9d2249e2ed4293c5aad7c87f4f59142b393
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46389000"
---
# <a name="colecontrolmodule-class"></a>Класс COleControlModule

Базовый класс, от которого необходимо наследовать объект модуля элемента управления OLE.

## <a name="syntax"></a>Синтаксис

```
class COleControlModule : public CWinApp
```

## <a name="remarks"></a>Примечания

Этот класс предоставляет функции-члены для инициализации модуля вашего элемента управления. Каждый модуль управления OLE, который использует библиотеки Microsoft Foundation classes может содержать только один объект, производный от `COleControlModule`. Этот объект создается в том случае, при создании других глобальных объектов C++. Объявите в производный `COleControlModule` объекта на глобальном уровне.

Дополнительные сведения об использовании `COleControlModule` , представлена в разделе [CWinApp](../../mfc/reference/cwinapp-class.md) класса и в статье [элементы управления ActiveX](../../mfc/mfc-activex-controls.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWinThread](../../mfc/reference/cwinthread-class.md)

[CWinApp](../../mfc/reference/cwinapp-class.md)

`COleControlModule`

## <a name="requirements"></a>Требования

**Заголовок:** afxctl.h

## <a name="see-also"></a>См. также

[Пример MFC TESTHELP](../../visual-cpp-samples.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)



