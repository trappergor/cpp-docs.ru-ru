---
title: Работа с документами и представлениями | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], documents
- MFC [C++], views
- views [C++], MFC
- documents [C++], MFC
ms.assetid: 349b142d-1c5a-4b99-9de4-241e41d3d2f1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c3879c6a29f95cc908d12c0b899214b521f46686
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50060447"
---
# <a name="working-with-documents-and-views"></a>Работа с документами и представлениями

Библиотека Microsoft Foundation Classes (MFC) зависит от архитектуры document/view, для его возможностей. Как правило документ используется для хранения данных и представления их отображения в клиентской области окна фрейма и управляет взаимодействием пользователя с данными. Представление взаимодействует с документом для получения и обновления данных. Можно использовать классы баз данных с помощью платформы или без него.

Дополнительные сведения об использовании классов базы данных в платформе, см. в разделе [MFC: использование классов базы данных с документами и представлениями](../../data/mfc-using-database-classes-with-documents-and-views.md).

По умолчанию мастер приложений MFC создает скелет приложения без поддержки базы данных. Тем не менее можно выбрать параметры, обеспечивающие минимальную поддержку баз данных или более полную поддержку на основе форм. Дополнительные сведения о параметрах мастера приложений см. в разделе [Поддержка баз данных, мастер приложений MFC](../../mfc/reference/database-support-mfc-application-wizard.md).

Также можно использовать классы баз данных без использования полный документ/представление архитектуры. Дополнительные сведения см. в разделе [MFC: использование классов базы данных без документов и представлений](../../data/mfc-using-database-classes-without-documents-and-views.md).

## <a name="see-also"></a>См. также

[ODBC и MFC](../../data/odbc/odbc-and-mfc.md)