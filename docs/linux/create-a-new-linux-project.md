---
title: Создание проекта C++ для Linux в Visual Studio
ms.date: 06/07/2019
ms.assetid: 5d7c1d67-bc31-4f96-8622-2b4cf91372fd
ms.openlocfilehash: e39e60c906901420a4809c22b4f4e71d3b621da1
ms.sourcegitcommit: 8adabe177d557c74566c13145196c11cef5d10d4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2019
ms.locfileid: "66821628"
---
# <a name="create-a-new-linux-project"></a>Создание проекта Linux

::: moniker range="vs-2015"

Проекты Linux, доступные в Visual Studio 2017 и более поздние версии.

::: moniker-end

Сначала убедитесь, что вы установили **рабочую нагрузку разработки для Linux** в Visual Studio. См. дополнительные сведения о [скачивании, установке и настройке рабочей нагрузки для Linux](download-install-and-setup-the-linux-development-workload.md).

При создании нового C++ проекта для Linux в Visual Studio, вы можете создать проект Visual Studio или проект CMake. В этой статье описывается создание проекта Visual Studio. Сведения о том, как создавать и изменять существующие проекты CMake см. в разделе [Настройка проекта Linux CMake ](cmake-linux-project.md).

## <a name="to-create-a-new-linux-project"></a>Для создания нового проекта Linux

Чтобы создать новый проект Linux в Visual Studio, выполните следующие действия.

::: moniker range="vs-2019"

1. Выберите **Файл > Создать проект** в меню Visual Studio или нажмите клавиши **Ctrl + Shift + N**.
1. Задайте **языка** для **C++** и выполните поиск «Linux». Выберите тип проекта для создания, а затем выберите **Далее**. Введите **имя** и **расположение**и выберите **создать**.

   ![Новый проект Linux](media/newproject-vs2019.png)

::: moniker-end

::: moniker range="vs-2017"

1. Выберите **Файл > Создать проект** в меню Visual Studio или нажмите клавиши **Ctrl + Shift + N**.
1. Выберите **Visual C++ > кроссплатформенный > Linux** узел, а затем выберите тип проекта для создания. Введите **имя** и **расположение**и выберите **ОК**.

   ![Новый проект Linux](media/newproject.png)

::: moniker-end

   | Тип проекта | Описание |
   | ------------ | --- |
   | **Blink (Raspberry)**           | Проект, предназначенный для устройства Raspberry Pi, с помощью примера кода, который включает и отключает светодиодный Индикатор |
   | **Консольное приложение (Linux)** | Проект, предназначенный для любого компьютера Linux с помощью примера кода, который выводит текст на консоль |
   | **Пустой проект (Linux)**       | Проект, предназначенный для любого компьютера Linux, без образца кода |
   | **Проект Makefile (Linux)**    | Проект, предназначенный для любого компьютера Linux, созданные с помощью стандартной системы сборки Makefile |

## <a name="next-steps"></a>Следующие шаги

[Настройка проекта Linux](configure-a-linux-project.md)
