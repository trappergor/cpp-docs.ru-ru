---
title: "Поддержка OLE: Реализация MFC | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IMarshall
- IMoniker
dev_langs:
- C++
helpviewer_keywords:
- MFC libraries, implementing
- OLE MFC library implementation
- OLE IMarshal interface
- IMoniker interface, MFC
- IMarshall class [MFC]
- OLE, compound files
- OLE IMoniker interface
- OLE IUnknown
ms.assetid: 2b67016a-d78e-4d60-925f-c28ec8fb6180
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 530cc14135fd38e2177e00dc87974e96ffe24b6c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ole-background-mfc-implementation"></a>Поддержка OLE. Реализация MFC
Из-за размера и сложности необработанные OLE API-интерфейса может быть очень длительной вызов его непосредственно для создания приложений OLE. Реализация библиотеки классов Microsoft Foundation OLE предназначена для того, чтобы уменьшить объем работы, что требуется для создания полнофункциональных, поддерживающими OLE приложений.  
  
 В этой статье описываются части OLE API, которые не были реализованы в MFC. Обсуждение также объясняется, что реализуется сопоставление OLE части пакета Windows SDK.  
  
##  <a name="_core_portions_of_ole_not_implemented_by_the_class_library"></a>Некоторые части OLE не реализован в библиотеке классов  
 Несколько интерфейсов и возможности OLE не предоставляются непосредственно MFC. Если требуется использовать эти функции можно вызывать непосредственно OLE API.  
  
 IMoniker-интерфейс  
 `IMoniker` Интерфейс реализуется библиотека классов (например, `COleServerItem` класса), но ранее не были предоставляемые программиста. Дополнительные сведения об этом интерфейсе см. в разделе OLE моникер реализации раздела OLE пакета Windows SDK. Тем не менее, см. также класс [CMonikerFile](../mfc/reference/cmonikerfile-class.md) и [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md).  
  
 IUnknown и IMarshal интерфейсы  
 **IUnknown** интерфейс реализуется библиотеку классов, но недоступен для программиста. **IMarshal** интерфейса не реализован в библиотеке классов, но используется для внутренних целей. Серверы автоматизации, построенных с использованием библиотеки классов, уже имеют маршалинг встроенных возможностей.  
  
 DOCFILES (составные файлы)  
 Составные файлы частично поддерживаются библиотеки классов. Ни одна из функций, которые напрямую манипулировать составные файлы после создания поддерживаются. MFC использует класс **COleFileStream** для поддержки обработки потоков с функциями стандартный файл. Дополнительные сведения см. в статье [контейнеры: составных файлов](../mfc/containers-compound-files.md).  
  
 В процессе серверами и дескрипторами объектов  
 Внутрипроцессные серверы и обработчики объекта позволяет реализовать данные визуального редактирования или полной модели объектов компонентов (COM) объектов в библиотеке динамической компоновки (DLL). Чтобы сделать это, можно реализовать библиотеки DLL, прямой вызов OLE API. Тем не менее при создании сервера автоматизации и сервер не имеет пользовательского интерфейса, можно использовать мастер приложений использовать ваш сервер в процессе и помещать его полностью в библиотеку DLL. Дополнительные сведения об этих темах см. в разделе [серверы автоматизации](../mfc/automation-servers.md).  
  
> [!TIP]
>  Самый простой способ реализации сервера автоматизации будет помещен в библиотеку DLL. MFC поддерживает такой подход.  
  
 Дополнительные сведения о том, как классы Microsoft Foundation OLE реализуют интерфейсы OLE см. Технические примечания MFC [38](../mfc/tn038-mfc-ole-iunknown-implementation.md), [39](../mfc/tn039-mfc-ole-automation-implementation.md), и [40](../mfc/tn040-mfc-ole-in-place-resizing-and-zooming.md).  
  
## <a name="see-also"></a>См. также  
 [Поддержка OLE](../mfc/ole-background.md)   
 [Поддержка OLE. Стратегии реализации](../mfc/ole-background-implementation-strategies.md)

