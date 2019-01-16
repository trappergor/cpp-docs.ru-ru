---
title: Как выполнить Непосредственное создание экземпляра компонентов WRL
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 1a9fa011-0cee-4abf-bf83-49adf53ff906
ms.openlocfilehash: 3caa29125de0de8cbe73379b8d7244206a5f9229
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54336825"
---
# <a name="how-to-instantiate-wrl-components-directly"></a>Как выполнить Непосредственное создание экземпляра компонентов WRL

Сведения об использовании Windows шаблонов среды выполнения C++ Library (WRL)[Microsoft::wrl:: make](make-function.md) и [Microsoft::WRL::Details::MakeAndInitialize](makeandinitialize-function.md) для создания экземпляра компонента из модуля, Определяет это.

С помощью создания компонентов напрямую можно уменьшить нагрузку, когда нет необходимости использовать фабрики классов или другие механизмы. Можно создать компонент напрямую в обоих приложениях универсальной платформы Windows и в настольных приложениях.

Чтобы научиться использовать библиотека шаблонов C++ среды выполнения Windows для создания классического компонента COM и его экземпляра из внешнего приложения, см. в разделе [как: Создание классического компонента COM](how-to-create-a-classic-com-component-using-wrl.md).

Здесь приведено два примера. В первом примере используется функция `Make` для создания экземпляра компонента. Во втором примере для создания компонента, который может создать ошибку во время построения, используется функция `MakeAndInitialize`. (Так как модель COM обычно использует значения HRESULT вместо исключений, чтобы показать ошибки, COM-типом обычно не вызывает из своего конструктора. Функция `MakeAndInitialize` позволяет компоненту проверить его аргументы построения с помощью метода `RuntimeClassInitialize`). Оба примера определяют базовый интерфейс ведения журнала и реализуют этот интерфейс, определяя класс, который выводит сообщения в окно консоли.

> [!IMPORTANT]
> Нельзя использовать `new` оператор создавать экземпляры компонент и библиотека шаблонов C++ среды выполнения Windows. Поэтому всегда рекомендуется использовать функцию `Make` или `MakeAndInitialize`, чтобы создать компонент напрямую.

### <a name="to-create-and-instantiate-a-basic-logger-component"></a>Создание базового компонента средства ведения журнала и его экземпляров

1. В Visual Studio создайте **консольное приложение Win32** проекта. Например, назовите проект, *WRLLogger*.

2. Добавить **файл Midl (.idl)** в проект файл, введите имя файла `ILogger.idl`, а затем добавьте следующий код:

   [!code-cpp[wrl-logger-make#1](../codesnippet/CPP/how-to-instantiate-wrl-components-directly_1.idl)]

3. Используйте указанный ниже код, чтобы заменить содержимое `WRLLogger.cpp`.

   [!code-cpp[wrl-logger-make#2](../codesnippet/CPP/how-to-instantiate-wrl-components-directly_2.cpp)]

### <a name="to-handle-construction-failure-for-the-basic-logger-component"></a>Обработка сбоя построения для базового компонента средства ведения журнала

1. Замените определение класса `CConsoleWriter` следующим кодом: Эта версия содержит частную строковую переменную-член и переопределяет метод `RuntimeClass::RuntimeClassInitialize`. Метод `RuntimeClassInitialize` завершается неудачей, если вызов `SHStrDup` завершается неудачей.

   [!code-cpp[wrl-logger-makeandinitialize#1](../codesnippet/CPP/how-to-instantiate-wrl-components-directly_3.cpp)]

2. Замените `wmain` следующим кодом: Эта версия использует `MakeAndInitialize` для создания экземпляра `CConsoleWriter` объекта и проверяет результат HRESULT.

   [!code-cpp[wrl-logger-makeandinitialize#2](../codesnippet/CPP/how-to-instantiate-wrl-components-directly_4.cpp)]

## <a name="see-also"></a>См. также

[Библиотека шаблонов C++ среды выполнения Windows (WRL)](windows-runtime-cpp-template-library-wrl.md)<br/>
[Microsoft::WRL::Make](make-function.md)<br/>
[Microsoft::WRL::Details::MakeAndInitialize](makeandinitialize-function.md)