---
title: Функция-член InitInstance
ms.date: 11/04/2016
f1_keywords:
- InitInstance
helpviewer_keywords:
- InitInstance method [MFC]
- applications [MFC], initializing
- MFC, initializing
- initializing MFC applications
ms.assetid: 4ef09267-ff7f-4c39-91a0-57454a264f83
ms.openlocfilehash: c96d009cf19981a475209233ee397af1cdcb352d
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57289394"
---
# <a name="initinstance-member-function"></a>Функция-член InitInstance

Операционная система Windows позволяет запускать несколько копий или «экземпляр» того же приложения. `WinMain` вызовы [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) каждый раз при запуске нового экземпляра приложения.

Стандартный `InitInstance` реализации, созданные с помощью мастера приложений MFC выполняет следующие задачи:

- В качестве его центра действие создает шаблоны документов, которые в свою очередь создают документы, представления и окна фрейма. Описание этого процесса, см. в разделе [Создание шаблонов документов](../mfc/document-template-creation.md).

- Загружает параметры стандартный файл из INI-файла или реестра Windows, включая имена самых последних использовавшихся файлов.

- Регистрирует один или несколько шаблонов документов.

- Приложение MDI создает главное окно.

- Обрабатывает командной строки для открытия документа указаны в командной строке или открыть новый, пустой документ.

Можно добавить код инициализации или изменить код, написанный с помощью мастера.

> [!NOTE]
>  MFC-приложения должны инициализироваться как однопотоковое подразделение (STA). При вызове метода [CoInitializeEx](/windows/desktop/api/combaseapi/nf-combaseapi-coinitializeex) в вашей `InitInstance` переопределения, укажите COINIT_APARTMENTTHREADED (а не COINIT_MULTITHREADED).

## <a name="see-also"></a>См. также

[CWinApp: Класс приложений](../mfc/cwinapp-the-application-class.md)
