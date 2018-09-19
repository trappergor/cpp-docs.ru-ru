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
ms.openlocfilehash: 64046eab403dca8da630c9c5324d320e0c79d4cc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054302"
---
# <a name="com-10-support-in-atl-projects"></a>Поддержка COM + 1.0 в проектах ATL

Можно использовать [мастер проектов ATL](../../atl/reference/creating-an-atl-project.md) для создания проекта с базовой поддержкой компонентов COM + 1.0.

COM + 1.0 предназначена для разработки распределенных приложений на основе компонентов. Он также предоставляет инфраструктуру времени выполнения для развертывания и управления этими приложениями.

При выборе **поддержки COM + 1.0** флажок, мастер изменяет скрипт построения на этапе связывания. В частности COM + 1.0 проекта ссылки на следующие библиотеки:

- Comsvcs.lib

- Mtxguid.lib

При выборе **поддержки COM + 1.0** флажок, вы также можете выбрать **регистрации компонента поддержки**. Регистрации компонента позволяет объекту COM + 1.0 получить список компонентов, регистрировать компоненты или отменяет регистрацию компонентов (по отдельности или все сразу).

## <a name="see-also"></a>См. также

[Основы COM-объектов ATL](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[Программирование с использованием ATL и кода среды выполнения C](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[Конфигурации проектов ATL по умолчанию](../../atl/reference/default-atl-project-configurations.md)

