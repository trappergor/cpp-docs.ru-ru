---
title: Свойства отладчика Android (C++)
ms.date: 10/23/2017
ms.assetid: 789f7a1c-38b4-41d0-809b-14f4d96c8116
f1_keywords:
- VC.Project.AndroidDebugger.DebuggerType
- VC.Project.AndroidDebugger.AndroidDeviceID
- VC.Project.AndroidDebugger.PackagePath
- VC.Project.AndroidDebugger.LaunchActivity
ms.openlocfilehash: 3ac896b384181e4e2b436368f39a343d35fe321a
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79470277"
---
# <a name="android-debugger-properties"></a>Свойства отладчика Android

| Свойство | Description | Варианты |
|--|--|--|
| Тип отладчика | Указывает тип кода для отладки. | **Только машинный код**<br /><br />**Только Java** |
| Целевой объект отладки | Указывает эмулятор или устройство для использования при отладке. Если эмуляторы не запущены, используйте "Диспетчер виртуальных устройств Android (AVD)" для запуска устройства. |
| Пакет для запуска | Указывает расположение *APK-файла*, подлежащего отладке. Этот параметр запускает пакет (APK) при отладке приложения. |
| Действие запуска | Действие Android для запуска приложения должно соответствовать использованному в манифесте. Нажмите кнопку "Применить", чтобы извлечь список из файла *AndroidManifest.xml* и динамически заполнить его. |
| Дополнительные пути поиска символов | Дополнительный путь поиска для символов отладки. |
| Дополнительные пути поиска исходных файлов Java | Дополнительные пути поиска для исходных файлов Java (применяется исключительно для типа отладчика "Только Java"). |
