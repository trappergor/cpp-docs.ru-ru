---
title: Ошибка времени выполнения C R6025
ms.date: 11/04/2016
f1_keywords:
- R6025
helpviewer_keywords:
- R6025
ms.assetid: afa06d98-9c36-445b-b3e7-b6409bc8e779
ms.openlocfilehash: 6e184ba24ad535697a727276a980fd082625e082
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218056"
---
# <a name="c-runtime-error-r6025"></a>Ошибка времени выполнения C R6025

чисто виртуальный вызов функции

> [!NOTE]
> Если при запуске приложения возникло это сообщение об ошибке, работа приложения была завершена из-за внутренней проблемы. Наиболее распространенной причиной этой ошибки является ошибка в приложении или повреждение установки.
>
> Для устранения этой ошибки попробуйте выполнить следующие действия:
>
> - Используйте страницу **приложения и компоненты** или **программы и компоненты** на **панели управления** , чтобы восстановить или переустановить программу.
> - Проверьте **Центр обновления Windows** на **панели управления** для обновлений программного обеспечения.
> - Проверьте наличие обновленной версии приложения. Если проблема не исчезнет, обратитесь к поставщику приложения.

**Сведения для программистов**

Не был создан экземпляр объекта для обработки чистого вызова виртуальной функции.

Эта ошибка вызвана вызовом виртуальной функции в абстрактном базовом классе с помощью указателя, созданного приведением к типу производного класса, но фактически является указателем на базовый класс. Это может произойти при приведении типа **`void`** <strong>\*</strong> к указателю на класс, когда **`void`** <strong>\*</strong> был создан во время создания базового класса.
