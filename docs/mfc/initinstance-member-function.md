---
title: "Функция-член InitInstance | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- InitInstance
dev_langs:
- C++
helpviewer_keywords:
- InitInstance method [MFC]
- applications [MFC], initializing
- MFC, initializing
- initializing MFC applications
ms.assetid: 4ef09267-ff7f-4c39-91a0-57454a264f83
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 96042b4d2931fb3709f992f6e43e408c919fe014
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="initinstance-member-function"></a>Функция-член InitInstance
Операционная система Windows позволяет запускать несколько копий или «экземпляр» того же приложения. `WinMain`вызовы [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) каждый раз при запуске нового экземпляра приложения.  
  
 Стандартные `InitInstance` реализацию, созданные с помощью мастера приложений MFC выполняет следующие задачи:  
  
-   В качестве его центра действие создает шаблонов документов, которые в свою очередь создают документы, представления и окна фрейма. Описание этого процесса см. в разделе [Создание шаблонов документов](../mfc/document-template-creation.md).  
  
-   Загружает параметры стандартный файл из INI-файле или в реестре Windows, включая имена недавно использовавшихся файлов.  
  
-   Регистрирует один или несколько шаблонов документов.  
  
-   Для приложения MDI создает фрейма главного окна.  
  
-   Обрабатывает командной строки для открытия документа, указанного в командной строке или открыть новый, пустой документ.  
  
 Можно добавить код инициализации или изменить код, написанный с помощью мастера.  
  
> [!NOTE]
>  Приложения MFC необходимо инициализировать в виде однопотокового подразделения (STA). При вызове метода [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279) в ваш `InitInstance` переопределения, укажите `COINIT_APARTMENTTHREADED` (а не `COINIT_MULTITHREADED`). Дополнительные сведения см. в статье PRB: приложение MFC перестает отвечать при инициализации приложения в качестве многопотокового подразделения (828643) в [http://support.microsoft.com/default.aspxscid=kb;en-us;828643](http://support.microsoft.com/default.aspxscid=kb;en-us;828643).  
  
## <a name="see-also"></a>См. также  
 [CWinApp: класс приложений](../mfc/cwinapp-the-application-class.md)
