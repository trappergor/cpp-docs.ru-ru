---
title: Поддержка COM + 1.0 в проектах ATL | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.appwiz.ATL.MTS
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, COM+ 1.0 support
ms.assetid: 51fb08ac-d632-4657-a4e0-d3f989f0b6f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 06a9e6cd4a374f0941b360a3f8f24f61e4b46a6a
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43763302"
---
# <a name="com-10-support-in-atl-projects"></a>Поддержка COM + 1.0 в проектах ATL

Можно использовать [мастер проектов ATL](../../atl/reference/creating-an-atl-project.md) для создания проекта с базовой поддержкой компонентов COM + 1.0.

COM + 1.0 предназначена для разработки распределенных приложений на основе компонентов. Он также предоставляет инфраструктуру времени выполнения для развертывания и управления этими приложениями.

При выборе **поддержки COM + 1.0** флажок, мастер изменяет скрипт построения на этапе связывания. В частности COM + 1.0 проекта ссылки на следующие библиотеки:

- Comsvcs.lib

- Mtxguid.lib

При выборе **поддержки COM + 1.0** флажок, вы также можете выбрать **регистрации компонента поддержки**. Регистрации компонента позволяет объекту COM + 1.0 получить список компонентов, регистрировать компоненты или отменяет регистрацию компонентов (по отдельности или все сразу).

## <a name="see-also"></a>См. также

[Основы COM-объектов ATL](../../atl/fundamentals-of-atl-com-objects.md)   
[Программирование с использованием ATL и кода среды выполнения C](../../atl/programming-with-atl-and-c-run-time-code.md)   
[Конфигурации проектов ATL по умолчанию](../../atl/reference/default-atl-project-configurations.md)

