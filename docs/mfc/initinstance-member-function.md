---
title: Функция-член InitInstance | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d026665a48d038092031bf4b632b7ef676124196
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43198179"
---
# <a name="initinstance-member-function"></a>Функция-член InitInstance
Операционная система Windows позволяет запускать несколько копий или «экземпляр» того же приложения. `WinMain` вызовы [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) каждый раз при запуске нового экземпляра приложения.  
  
 Стандартный `InitInstance` реализации, созданные с помощью мастера приложений MFC выполняет следующие задачи:  
  
-   В качестве его центра действие создает шаблоны документов, которые в свою очередь создают документы, представления и окна фрейма. Описание этого процесса, см. в разделе [Создание шаблонов документов](../mfc/document-template-creation.md).  
  
-   Загружает параметры стандартный файл из INI-файла или реестра Windows, включая имена самых последних использовавшихся файлов.  
  
-   Регистрирует один или несколько шаблонов документов.  
  
-   Приложение MDI создает главное окно.  
  
-   Обрабатывает командной строки для открытия документа указаны в командной строке или открыть новый, пустой документ.  
  
 Можно добавить код инициализации или изменить код, написанный с помощью мастера.  
  
> [!NOTE]
>  MFC-приложения должны инициализироваться как однопотоковое подразделение (STA). При вызове метода [CoInitializeEx](/windows/desktop/api/combaseapi/nf-combaseapi-coinitializeex) в вашей `InitInstance` переопределения, укажите COINIT_APARTMENTTHREADED (а не COINIT_MULTITHREADED). Дополнительные сведения см. в статье PRB: MFC приложение перестает отвечать на запросы при инициализации приложения в качестве многопотокового подразделения (828643) в [ http://support.microsoft.com/default.aspxscid=kb; en-us; 828643](http://support.microsoft.com/default.aspxscid=kb;en-us;828643).  
  
## <a name="see-also"></a>См. также  
 [CWinApp: класс приложений](../mfc/cwinapp-the-application-class.md)
