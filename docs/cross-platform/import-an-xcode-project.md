---
title: Импорт проекта Xcode
ms.date: 10/17/2019
ms.assetid: aa4b8161-d98f-4a1a-9db3-520133bfc82f
ms.openlocfilehash: 709060e053852f4518a842467ccfb7f0ed760ba2
ms.sourcegitcommit: a673f6a54cc97e3d4cd032b10aa8dce7f0539d39
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "79470049"
---
# <a name="import-an-xcode-project"></a>Импорт проекта Xcode

Средства Visual Studio для разработки кросс-платформенных мобильных приложений на языке С++ позволяют переносить проекты Xcode в Visual Studio, в котором вы можете создавать кросс-платформенные библиотеки и обмениваться кодом с другими проектами. Мастер импорта из Xcode упрощает процесс импорта проектов и отделения кода С++ в целевых объектах Xcode для использования в качестве статической библиотеки или проекта общего кода. Вы можете управлять своим кодом, связанным с iOS, в Visual Studio и по-прежнему использовать Xcode для раскадровки и сборки проекта. Сведения о легком перемещении кода между Visual Studio и Xcode, см. в разделе [Изменения в синхронизации между Xcode и Visual Studio](sync-changes-between-xcode-and-visual-studio.md).

## <a name="use-the-import-from-xcode-wizard"></a>Использование мастера импорта из Xcode

В этой статье приведены сведения о перемещении проекта Xcode в Visual Studio, а также об использовании преимуществ совместного использования кода и кросс-платформенных решений. Для импорта, экспорта и сборки проекта необходимо выполнить сопряжение Mac с Visual Studio. Инструкции по настройке сопряжения см. в статье [Установка и настройка средств сборки для iOS](../cross-platform/install-and-configure-tools-to-build-using-ios.md). Для использования мастера импорта из Xcode также необходимо предоставить общий доступ к своему проекту по сети или перенести его на свой компьютер с Visual Studio.

### <a name="import-from-xcode"></a>Импорт из Xcode

1. В меню **Файл** выберите **Новый документ**, **Импорт**, **Импорт из Xcode**. Эта команда запускает диалоговое окно мастера **Импорт из мастера Xcode**.

   ![Выбор целевого проекта Xcode для импорта](../cross-platform/media/cppmdd-u2-importxcode-choose.png "Выбор целевого проекта Xcode для импорта")

1. В панели **Выбор проекта** выберите кнопку "Обзор", чтобы выбрать файл Xcode *.pbxproj*. Перейдите к файлу проекта в диалоговом окне **Выбрать файл проекта Xcode**, а затем выберите **Открыть**.

   ![Выбор файла проекта в окне Выбор файла проекта Xcode](../cross-platform/media/cppmdd-u2-importxcode-browse.png "Выбор файла проекта в окне Выбор файла проекта Xcode")

   В мастере импорта из Xcode выберите **Далее**.

1. В области **Целевые объекты назначения** выберите целевые объекты в проекте Xcode, которые будут импортированы в проекты Visual Studio. Целевые объекты Xcode аналогичны целевым объектам в проектах Visual Studio; большинство из них представляют собой сочетание кода и ресурсов, которые образуют двоичный файл. Мастер импорта из Xcode позволяет импортировать только те объекты, которые производят двоичную библиотеку, а не статическую, в качестве объектов назначения. Предметом следующего шага являются цели статических библиотек Xcode.

   ![Импорт из панели Цели назначения мастера Xcode](../cross-platform/media/cppmdd-u2-importxcode-destination.jpg "Импорт из панели Цели назначения мастера Xcode")

   Для каждого целевого объекта, выбранного в разделе **Целевые объекты для импорта**, мастер автоматически определяет файлы кода C++, которые можно выделить в отдельный проект статической библиотеки, и помещает их в раздел **Элементы проекта C++** . Другие коды и ресурсы остаются в разделе **Элементы проекта Xcode**. После окончания импорта они станут отдельной статической библиотекой и проектами приложения в Visual Studio. По умолчанию модульные тесты и целевые объекты платформы не разбиваются на отдельные проекты.

   Чтобы изменить файлы в каждом проекте воспользуйтесь кнопками со стрелками вверх и вниз. После выбора файлов для каждого проекта нажмите кнопку **Далее** для продолжения.

1. В области **Целевые объекты библиотеки** выберите целевые объекты статической библиотеки в проекте Xcode, которые будут импортированы в проекты Visual Studio. В этой области можно выбрать, какие файлы будут добавлены в проект с общим кодом, а какие — в проект статической библиотеки. В каждом из целевых объектов в списке **Целевые объекты для импорта** можно управлять тем, какие файлы будут добавлены в **Элементы проекта общего кода** и в **Элементы проекта статической библиотеки** с помощью кнопок со стрелками вверх и вниз.

   ![Импорт из панели Цели библиотеки Xcode](../cross-platform/media/cppmdd-u2-importxcode-library.jpg "Импорт из панели Цели библиотеки Xcode")

   С помощью проекта общего кода можно обмениваться файлами исходного кода между проектами в Visual Studio. Сборка кода происходит в рамках проекта, в который он входит, а не в рамках отдельного проекта. Проекты, которые содержат общий код, могут иметь различную архитектуру и конфигурацию. Проект с общим кодом — это лучший способ создать единый проект, содержащий код, который может быть собран для многих типов платформ.

   После выбора файлов для каждого проекта нажмите кнопку **Далее** для продолжения.

1. Используйте панель **Глобальные свойства**, чтобы задать путь поиска платформы и путь поиска включенного заголовка для всех iOS-проектов в Visual Studio. Visual Studio использует эти пути для просмотра исходного кода и для IntelliSense. С помощью этих глобальных путей удобно создавать проекты iOS, которые используют общий набор заголовков и платформ.

   ![Импорт из панели Xcode Глобальные свойства](../cross-platform/media/cppmdd-u2-importxcode-global.jpg "Импорт из панели Xcode Глобальные свойства")

   Эти глобальные пути также можно задать в Visual Studio в диалоговом окне **Параметры**. Чтобы их найти, в меню **Сервис** выберите **Параметры**. В диалоговом окне **Параметры** разверните **Кросс-платформа** > **C+++**  > **iOS** > **Глобальные свойства**.

   Чтобы продолжить, нажмите кнопку **Далее** .

1. Область **Платформы** используется для настройки путей, которые используются Visual Studio для просмотра файлов и для IntelliSense. Visual Studio должны быть доступны пути для каждой платформы, на которую ссылается ваш проект Xcode. Мастер проверяет ссылки на платформы в проектах Xcode и отображает, может ли Visual Studio найти платформу. Все пути, которые уже были настроены в окне Глобальные свойства, должны быть доступны для Visual Studio. Исключения указаны в списке Платформы. Для каждой платформы, которая помечена символом "X", укажите путь к платформе на компьютере Visual Studio. Для указания пути можно воспользоваться кнопкой "Обзор" ( **...** ). Откроется окно **Выбор папки**. Можно указать путь к локальной копии платформы или путь к сетевой папке на компьютере Mac.

   ![Импорт из панели Xcode Платформы](../cross-platform/media/cppmdd-u2-importxcode-frameworks.jpg "Импорт из панели Xcode Платформы")

   Чтобы продолжить, нажмите кнопку **Далее** .

1. В области **Параметры проекта** можно изменить платформу и включить параметры путей поиска заголовков для каждого проекта, создаваемого мастером. В этой области задаются пути для определенного проекта, которые отличаются от глобальных параметров.

   Чтобы задать путь для конкретного проекта, в раскрывающемся списке **Конечный проект** выберите файл проекта. Затем установите значения в элементах управления **Framework Search Path** и **Include Header Search Path**. Для указания пути можно воспользоваться кнопкой "Обзор" ( **...** ) рядом с каждым элементом управления. Откроется окно **Выбор папки**.

   ![Импорт из панели Xcode Проекты](../cross-platform/media/cppmdd-u2-importxcode-projects.jpg "Импорт из панели Xcode Проекты")

   Если с этим компьютером не был связан удаленный компьютер Mac в Visual Studio, отображается ссылка **Настроить удаленный компьютер**. Инструкции по настройке сопряжения см. в статье [Установка и настройка средств сборки для iOS](../cross-platform/install-and-configure-tools-to-build-using-ios.md).

   Чтобы импортировать проект Xcode с помощью параметров мастера, выберите **Импорт**.

   Импорт с помощью мастера Xcode создает в Visual Studio проекты, соответствующие выбранным целям проекта Xcode. Код, который можно использовать совместно с другими проектами C++, выделяется в отдельные проекты общего кода и проекты статических библиотек. Оставшийся код помещается в проекты библиотек и приложений iOS, сборку которых можно выполнить удаленно с помощью Visual Studio. Дополнительные сведения о перемещении кода между Visual Studio и Xcode см. в разделе [Синхронизация изменений между Xcode и Visual Studio](../cross-platform/sync-changes-between-xcode-and-visual-studio.md).

## <a name="see-also"></a>См. также раздел

- [Установка Visual C++ для разработки кроссплатформенных мобильных приложений на языке C++](../cross-platform/install-visual-cpp-for-cross-platform-mobile-development.md)