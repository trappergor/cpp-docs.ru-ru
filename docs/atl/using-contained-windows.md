---
title: С помощью автономной Windows | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ATL, windows
- windows [C++], ATL
- contained windows in ATL
ms.assetid: 7b3d79e5-b569-413f-9b98-df4f14efbe2b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cc17925e36e0e224a657177d0aa18912c564efed
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/05/2018
ms.locfileid: "37850804"
---
# <a name="using-contained-windows"></a>С помощью автономной Windows
ATL реализует размещенных окон с [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md). Содержащееся окно представляет окно, которое передает сообщения между объект контейнера вместо их обработки в свой собственный класс.  
  
> [!NOTE]
>  Вы не обязательно должны быть производным от класса `CContainedWindowT` для использования размещенных окон.  
  
 С помощью автономной windows вы можете либо суперкласса существующего класса Windows или подкласс существующему окну. Для создания окна, является суперклассом существующих Windows класса, сначала укажите имя существующего класса в конструкторе для `CContainedWindowT` объекта. Затем вызовите `CContainedWindowT::Create`. Подкласс существующее окно не нужно указать имя класса Windows (pass NULL в конструктор). Просто вызовите `CContainedWindowT::SubclassWindow` метод с дескриптор окна подкласса.  
  
 Обычно используется размещенных окон, как данные-член класса контейнера. Контейнер не нужно быть окном; Тем не менее, он должен быть производным от [CMessageMap](../atl/reference/cmessagemap-class.md).  
  
 Содержащееся окно можно использовать схемы альтернативный сообщений для обработки сообщения. При наличии более одного содержащееся окно, следует объявить несколько дополнительного схемы сообщений, каждое из которых соответствует отдельный содержащееся окно.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример класса контейнера с помощью двух размещенных окон:  
  
 [!code-cpp[NVC_ATL_Windowing#67](../atl/codesnippet/cpp/using-contained-windows_1.h)]  
  
 Дополнительные сведения о размещенных окон, см. в разделе [SUBEDIT](../visual-cpp-samples.md) образца.  
  
## <a name="see-also"></a>См. также  
 [Классы окон](../atl/atl-window-classes.md)

