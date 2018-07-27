---
title: SDI и MDI | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- frame windows [MFC], SDI applications
- frame windows [MFC], MDI applications
- MFC, windows
- single document interface (SDI) [MFC], applications
- MDI [MFC], vs. SDI
ms.assetid: bb7239d9-4759-4f63-bfff-44a04b48c067
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: db63efe8d7e2622610bb56f5e6885b72b705093b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385808"
---
# <a name="sdi-and-mdi"></a>SDI и MDI
MFC упрощает работу с однооконный интерфейс (SDI) и приложений многодокументного интерфейса (MDI).  
  
 SDI-приложения разрешает только одно окно фрейма документа, открыть одновременно. MDI-приложения разрешает несколько документов фреймов, необходимо открыть в тот же экземпляр приложения. MDI-приложения имеет окна, в которой несколько MDI дочерних окон, которые фреймов самостоятельно, можно открыть, каждый из которых содержит отдельный документ. В некоторых приложениях дочерних окон может быть разных типов, таких как диаграммы и окна электронной таблицы. В этом случае в меню можно изменить как активируются дочерние окна MDI различных типов.  
  
> [!NOTE]
>  В среде Windows 95 и более поздних версиях приложений обычно представляют собой SDI, так как операционная система была внедрена представления «по центру документа».  
  
 Дополнительные сведения см. в разделе [документы, представления и платформа](../mfc/documents-views-and-the-framework.md).  
  
## <a name="see-also"></a>См. также  
 [Использование классов для создания приложений для Windows](../mfc/using-the-classes-to-write-applications-for-windows.md)
