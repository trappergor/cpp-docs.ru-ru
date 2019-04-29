---
title: Поддержка COM + 1.0 в проектах ATL
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.ATL.MTS
helpviewer_keywords:
- ATL projects, COM+ 1.0 support
ms.assetid: 51fb08ac-d632-4657-a4e0-d3f989f0b6f8
ms.openlocfilehash: 39a3597b8df833d89942e31b361f791b14ceb8c9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62278479"
---
# <a name="com-10-support-in-atl-projects"></a>Поддержка COM + 1.0 в проектах ATL

Можно использовать [мастер проектов ATL](../../atl/reference/creating-an-atl-project.md) для создания проекта с базовой поддержкой компонентов COM + 1.0.

COM + 1.0 предназначена для разработки распределенных приложений на основе компонентов. Он также предоставляет инфраструктуру времени выполнения для развертывания и управления этими приложениями.

При выборе **поддержки COM + 1.0** флажок, мастер изменяет скрипт построения на этапе связывания. В частности COM + 1.0 проекта ссылки на следующие библиотеки:

- comsvcs.lib

- Mtxguid.lib

При выборе **поддержки COM + 1.0** флажок, вы также можете выбрать **регистрации компонента поддержки**. Регистрации компонента позволяет объекту COM + 1.0 получить список компонентов, регистрировать компоненты или отменяет регистрацию компонентов (по отдельности или все сразу).

## <a name="see-also"></a>См. также

[Основы COM-объектов ATL](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[Программирование с использованием ATL и кода среды выполнения C](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[Конфигурации проектов ATL по умолчанию](../../atl/reference/default-atl-project-configurations.md)
