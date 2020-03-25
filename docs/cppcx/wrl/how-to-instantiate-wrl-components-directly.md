---
title: Практическое руководство. Непосредственное создание экземпляра компонентов WRL
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 1a9fa011-0cee-4abf-bf83-49adf53ff906
ms.openlocfilehash: f291e982d7f77c63821e5943a5867662ccd1b4fa
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213906"
---
# <a name="how-to-instantiate-wrl-components-directly"></a>Практическое руководство. Непосредственное создание экземпляра компонентов WRL

Узнайте, как использовать библиотеку шаблонов C++ среда выполнения Windows (WRL)[Microsoft:: WRL:: make](make-function.md) и [Microsoft:: WRL::D состояния:: MakeAndInitialize](makeandinitialize-function.md) для создания экземпляра компонента из модуля, который его определяет.

С помощью создания компонентов напрямую можно уменьшить нагрузку, когда нет необходимости использовать фабрики классов или другие механизмы. Экземпляр компонента можно создать непосредственно в универсальная платформа Windows приложениях и в классических приложениях.

Сведения об использовании библиотеки шаблонов среда выполнения Windows C++ для создания классического COM-компонента и его создания из внешнего рабочего стола см. в разделе [как создать классический COM-компонент](how-to-create-a-classic-com-component-using-wrl.md).

Здесь приведено два примера. В первом примере используется функция `Make` для создания экземпляра компонента. Во втором примере для создания компонента, который может создать ошибку во время построения, используется функция `MakeAndInitialize`. (Поскольку COM обычно использует значения HRESULT, а не исключения, для обозначения ошибок COM-тип обычно не создает из своего конструктора. `MakeAndInitialize` позволяет компоненту проверять свои аргументы конструктора с помощью метода `RuntimeClassInitialize`.) В обоих примерах определяется базовый интерфейс ведения журнала и реализуется этот интерфейс путем определения класса, записывающего сообщения в консоль.

> [!IMPORTANT]
> Вы не можете использовать оператор `new` для создания экземпляров компонентов C++ библиотеки шаблонов среда выполнения Windows. Поэтому всегда рекомендуется использовать функцию `Make` или `MakeAndInitialize`, чтобы создать компонент напрямую.

### <a name="to-create-and-instantiate-a-basic-logger-component"></a>Создание базового компонента средства ведения журнала и его экземпляров

1. В Visual Studio создайте проект **консольного приложения Win32** . Присвойте проекту имя, например *врллогжер*.

2. Добавьте в проект файл **MIDL (. IDL)** , присвойте файлу имя `ILogger.idl`, а затем добавьте следующий код:

   [!code-cpp[wrl-logger-make#1](../codesnippet/CPP/how-to-instantiate-wrl-components-directly_1.idl)]

3. Используйте следующий код, чтобы заменить содержимое `WRLLogger.cpp`.

   [!code-cpp[wrl-logger-make#2](../codesnippet/CPP/how-to-instantiate-wrl-components-directly_2.cpp)]

### <a name="to-handle-construction-failure-for-the-basic-logger-component"></a>Обработка сбоя построения для базового компонента средства ведения журнала

1. Замените определение класса `CConsoleWriter` следующим кодом: Эта версия содержит частную строковую переменную-член и переопределяет метод `RuntimeClass::RuntimeClassInitialize`. в случае сбоя вызова `SHStrDup` `RuntimeClassInitialize` происходит сбой.

   [!code-cpp[wrl-logger-makeandinitialize#1](../codesnippet/CPP/how-to-instantiate-wrl-components-directly_3.cpp)]

2. Замените `wmain` следующим кодом: Эта версия использует `MakeAndInitialize` для создания экземпляра объекта `CConsoleWriter` и проверяет результат HRESULT.

   [!code-cpp[wrl-logger-makeandinitialize#2](../codesnippet/CPP/how-to-instantiate-wrl-components-directly_4.cpp)]

## <a name="see-also"></a>См. также раздел

[Библиотека шаблонов C++ среды выполнения Windows (WRL)](windows-runtime-cpp-template-library-wrl.md)<br/>
[Microsoft:: WRL:: make](make-function.md)<br/>
[Microsoft:: WRL::D состояния:: MakeAndInitialize](makeandinitialize-function.md)
