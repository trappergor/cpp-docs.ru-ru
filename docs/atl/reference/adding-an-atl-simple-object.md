---
title: Добавление простого объекта ATL | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.codewiz.classes.adding.atl
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding objects
- objects [ATL]
- ATL, simple objects
ms.assetid: 9c57d2ef-0447-4c84-8982-3304b8e49847
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d1347fcebc6a3793cbe63ae356f7f9d2e03742cd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46109773"
---
# <a name="adding-an-atl-simple-object"></a>Добавление простого объекта ATL

Чтобы добавить объект ATL (Active Template Library) в проект, проект должен будут созданы как приложение ATL или как приложение MFC с поддержкой ATL. Вы можете использовать [Мастер проектов ATL](../../atl/reference/atl-project-wizard.md), чтобы создать приложение ATL, или [добавить объект ATL в свое приложение MFC](../../mfc/reference/adding-atl-support-to-your-mfc-project.md), чтобы реализовать поддержку ATL для приложения MFC.

Можно определить COM-интерфейсы для нового объекта ATL, при создании его, или добавить их позже с помощью [реализовать интерфейс](../../ide/implement-interface-wizard.md) команду в контекстном меню представления классов.

### <a name="to-add-an-atl-simple-object-to-your-atl-com-project"></a>Добавление простого объекта ATL в проект ATL COM

1. В любом **обозревателе решений** или [представление классов](/visualstudio/ide/viewing-the-structure-of-code), щелкните правой кнопкой мыши имя проекта, к которому вы хотите добавить простой объект ATL.

2. В контекстном меню выберите команду **Добавить**, а затем — **Добавить класс**.

3. В [Добавление класса](../../ide/add-class-dialog-box.md) диалоговом окне в области «Шаблоны» щелкните **простой объект ATL**, а затем нажмите кнопку **откройте** для отображения [мастер простых объектов ATL](../../atl/reference/atl-simple-object-wizard.md).

4. Задание дополнительных параметров для проекта на [параметры](../../atl/reference/options-atl-simple-object-wizard.md) странице мастера простой объект ATL.

5. Нажмите кнопку **Готово** добавлен объект в проект.

## <a name="see-also"></a>См. также

[Добавление класса](../../ide/adding-a-class-visual-cpp.md)<br/>
[Добавление нового интерфейса в проект ATL](../../atl/reference/adding-a-new-interface-in-an-atl-project.md)<br/>
[Добавление точек подключения к объектам](../../atl/adding-connection-points-to-an-object.md)<br/>
[Добавление метода](../../ide/adding-a-method-visual-cpp.md)<br/>
[Класс MFC](../../mfc/reference/adding-an-mfc-class.md)<br/>
[Добавление универсального класса C++](../../ide/adding-a-generic-cpp-class.md)

