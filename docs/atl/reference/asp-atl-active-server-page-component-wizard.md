---
title: ASP, мастер компонентов страницы активного сервера ATL | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.asp.asp
dev_langs:
- C++
helpviewer_keywords:
- ATL Active Server Page Component Wizard, ASP
ms.assetid: 4d8cafd6-5e12-4461-8911-29288896af3c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 63f945f90f6a862a3b16cd3dcc41859b0c21b984
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43761948"
---
# <a name="asp-atl-active-server-page-component-wizard"></a>ASP, мастер компонентов страницы активного сервера ATL

Эта страница мастер компонентов ATL Active Server страница используется для указания дополнительных параметров для обработки информации и состояний, относящихся к компоненту ASP.

**Необязательные методы**  
Добавляет необязательные методы ASP, **OnStartPage** и **OnEndPage**, вашего объекта. Необходимо выбрать этот параметр для задания любой Active Server Pages встроенные объекты. По умолчанию он выбран.

- **OnStartPage/OnEndPage** [OnStartPage](https://msdn.microsoft.com/library/ms691624.aspx) вызывается в первый раз, он пытается получить доступ к объекту. **OnEndPage** вызывается, когда объект заканчивает обработку сценария.

**Встроенный объект**  
Необходимо выбрать **OnStartPage/OnEndPage** параметр, чтобы задать все внутренние объекты ASP.

|Параметр|Описание|
|------------|-----------------|
|**Запрос**|Предоставляет доступ к внутренние Active Server Pages **запроса** объекта. Объект запроса используется для передачи HTTP-запроса.|
|**Ответ**|Предоставляет доступ к внутренние Active Server Pages **ответа** объекта. В ответ на запрос объект Response передает данные в браузер для отображения пользователю.|
|**Сеанс**|Предоставляет доступ к внутренние Active Server Pages **сеанса** объекта. **Сеанса** объект сохраняет сведения о текущем сеансе пользователя, хранит и получает сведения о состоянии.|
|**Приложение**|Предоставляет доступ к внутренние Active Server Pages **приложения** объекта. **Приложения** объекта управляет состоянием, который разделяется между несколькими объектами ASP.|
|**Сервер**|Предоставляет доступ к внутренние Active Server Pages **Server** объекта. **Server** объект позволяет создавать другие объекты ASP.|

## <a name="see-also"></a>См. также

[Мастер компонентов страницы активного сервера ATL](../../atl/reference/atl-active-server-page-component-wizard.md)   
[ASP-компонента ATL](../../atl/reference/adding-an-atl-active-server-page-component.md)

