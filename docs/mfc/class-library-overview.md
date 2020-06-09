---
title: Общие сведения о библиотеке классов
ms.date: 09/17/2019
f1_keywords:
- vc.classes.mfc
helpviewer_keywords:
- grouping MFC classes
- MFC, class library
- classes [MFC], MFC
- class libraries, MFC
- class libraries
ms.assetid: 9b0e3152-ac39-4f52-91b4-f20aa3a674aa
ms.openlocfilehash: bf30f1b0aa83ef002337b76601f04c7103963441
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84620746"
---
# <a name="class-library-overview"></a>Общие сведения о библиотеке классов

В этом обзоре классифицируются и описываются классы в библиотека Microsoft Foundation Class (MFC) версии 9,0. Классы в MFC вместе составляют платформу приложения — платформу приложения, написанную для Windows API. Задача программирования заключается в том, чтобы заполнять код, относящийся к конкретному приложению.

Классы библиотеки представлены в следующих категориях:

- [Корневой класс: CObject](root-class-cobject.md)

- [Классы архитектуры приложения MFC](mfc-application-architecture-classes.md)

  - [Классы поддержки приложений и потоков](application-and-thread-support-classes.md)

  - [Классы маршрутизации команд](command-routing-classes.md)

  - [Классы документов](document-classes.md)

  - [Классы представления (архитектура)](view-classes-architecture.md)

  - [Классы окна фрейма (архитектура)](frame-window-classes-architecture.md)

  - [Классы шаблонов документов](document-template-classes.md)

- [Классы Window, DIALOG и Control](window-dialog-and-control-classes.md)

  - [Классы окон фрейма (Windows)](frame-window-classes-windows.md)

  - [Классы представлений (Windows)](view-classes-windows.md)

  - [Классы диалоговых окон](dialog-box-classes.md)

  - [Классы элементов управления](control-classes.md)

  - [Классы панели элементов управления](control-bar-classes.md)

- [Классы рисования и печати](drawing-and-printing-classes.md)

  - [Классы вывода (контекст устройства)](output-device-context-classes.md)

  - [Классы инструмента рисования](drawing-tool-classes.md)

- [Классы простых типов данных](simple-data-type-classes.md)

- [Классы массивов, списков и схем](array-list-and-map-classes.md)

  - [Классы шаблонов для массивов, списков и сопоставлений](template-classes-for-arrays-lists-and-maps.md)

  - [Готовые к использованию классы массивов](ready-to-use-array-classes.md)

  - [Готовые классы списков](ready-to-use-list-classes.md)

  - [Готовые к использованию классы карт](ready-to-use-map-classes.md)

- [Классы файлов и баз данных](file-and-database-classes.md)

  - [Классов ввода-вывода файлов](file-i-o-classes.md)

  - [Классы DAO](dao-classes.md)

  - [Классы ODBC](odbc-classes.md)

  - [Классы OLE DB](ole-db-classes.md)

- [Классы Интернета и сети](internet-and-networking-classes.md)

  - [Классы сокетов Windows](windows-sockets-classes.md)

  - [Классы Win32 в Интернете](win32-internet-classes.md)

- [Классы OLE](ole-classes.md)

  - [Классы контейнера OLE](ole-container-classes.md)

  - [Серверные классы OLE](ole-server-classes.md)

  - [Классы перетаскивания и Передача данных классов OLE](ole-drag-and-drop-and-data-transfer-classes.md)

  - [Классы общих диалоговых окон OLE](ole-common-dialog-classes.md)

  - [Классы автоматизации OLE](ole-automation-classes.md)

  - [Классы элементов управления OLE](ole-control-classes.md)

  - [Классы активных документов](active-document-classes.md)

  - [Классы, связанные с OLE](ole-related-classes.md)

- [Классы отладки и исключений](debugging-and-exception-classes.md)

  - [Отладка классов поддержки](debugging-support-classes.md)

  - [Классы исключений](exception-classes.md)

В разделе [Общие принципы проектирования классов](general-class-design-philosophy.md) объясняется, как была РАЗРАБОТАНА библиотека MFC.

Общие сведения о платформе см. в разделе [Использование классов для написания приложений для Windows](using-the-classes-to-write-applications-for-windows.md). Некоторые из перечисленных выше классов являются классами общего назначения, которые можно использовать за пределами платформы и предоставляют полезные абстракции, такие как коллекции, исключения, файлы и строки.

Чтобы просмотреть наследование класса, используйте [диаграмму иерархия классов](hierarchy-chart.md).

В дополнение к классам, перечисленным в этом обзоре, Библиотека MFC содержит ряд глобальных функций, глобальных переменных и макросов. В разделе [макросы и глобальные классы MFC](reference/mfc-macros-and-globals.md)представлен обзор и подробное описание этих элементов, которые следуют алфавитному представлению классов MFC.

## <a name="see-also"></a>См. также раздел

[Приложения MFC для рабочего стола](mfc-desktop-applications.md)
