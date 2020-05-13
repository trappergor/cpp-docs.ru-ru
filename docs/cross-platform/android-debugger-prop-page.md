---
title: Свойства Android Debugger (КЗ)
ms.date: 10/23/2017
ms.assetid: 789f7a1c-38b4-41d0-809b-14f4d96c8116
f1_keywords:
- VC.Project.AndroidDebugger.DebuggerType
- VC.Project.AndroidDebugger.AndroidDeviceID
- VC.Project.AndroidDebugger.PackagePath
- VC.Project.AndroidDebugger.LaunchActivity
ms.openlocfilehash: 23fd871f030593607cf374870b96e09d8bc2da7a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374203"
---
# <a name="android-debugger-properties"></a>Свойства отладчика Android

| Свойство | Описание | Варианты |
|--|--|--|
| Тип отладчика | Указывает тип кода для отладки. | **Только коренные**<br /><br />**Только Java** |
| Целевой объект отладки | Указывает эмулятор или устройство для использования при отладке. Если эмуляторы не работают, используйте 'Android Virtual Device (AVD) Manager', чтобы запустить устройство. |
| Пакет для запуска | Определяет местоположение *.apk,* который будет отдипон. Эта опция запускает пакет (APK) при отладке приложения. |
| Действие запуска | Действие Android для запуска приложения должно соответствовать использованному в манифесте. Нажмите применить, чтобы получить список из *AndroidManifest.xml* и заполнить его динамически. |
| Дополнительные пути поиска символов | Дополнительный путь поиска для символов отладки. |
| Дополнительные пути поиска исходных файлов Java | Дополнительные пути поиска для исходных файлов Java (применяется исключительно для типа отладчика "Только Java"). |
