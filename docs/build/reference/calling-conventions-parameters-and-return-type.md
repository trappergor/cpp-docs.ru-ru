---
title: Соглашения о вызовах, параметры и тип возвращаемого значения
ms.date: 11/04/2016
helpviewer_keywords:
- calling conventions, helper functions
- helper functions, calling conventions
- helper functions, return types
ms.assetid: 0ffa4558-6005-4803-be95-7a8ec8837660
ms.openlocfilehash: 8343c17828040ca36b042cb99e0c51c37548d3b3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50654432"
---
# <a name="calling-conventions-parameters-and-return-type"></a>Соглашения о вызовах, параметры и тип возвращаемого значения

Прототип вспомогательной подпрограммы:

```
FARPROC WINAPI __delayLoadHelper2(
    PCImgDelayDescr pidd,
    FARPROC * ppfnIATEntry
);
```

### <a name="parameters"></a>Параметры

*pidd*<br/>
Указатель `const` на структуру `ImgDelayDescr` (см. файл delayimp.h), содержащую смещения различных данных, связанных с импортом, метку времени для информации о привязке и набор атрибутов, предоставляющих дополнительную информацию о содержимом дескриптора. В настоящее время имеется только один атрибут, `dlattrRva`, который указывает на то, что адреса в дескрипторе являются относительными виртуальными адресами (в противоположность виртуальным адресам).

Для определения `PCImgDelayDescr` структуры, см. в разделе [определение структуры и константы](../../build/reference/structure-and-constant-definitions.md).

*ppfnIATEntry*<br/>
Указатель на ячейку в таблице адресов импорта (IAT), загружаемого с задержкой, которую необходимо обновить, занеся в нее адрес импортированной функции. Вспомогательная подпрограмма должна сохранить то же самое значение, которое будет возвращено в это место.

## <a name="expected-return-values"></a>Ожидаемые возвращаемые значения

Если функция выполнена успешно, она возвращает адрес импортированной функции.

Если функция завершается с ошибкой, она создает исключение и возвращает 0. Возможны три типа исключений.

- Недопустимый параметр. Это исключение создается, если атрибуты в `pidd` указаны некорректно.

- Функции `LoadLibrary` не удалось загрузить указанную библиотеку DLL.

- Ошибка в функции `GetProcAddress`.

За обработку этих исключений отвечает разработчик.

## <a name="remarks"></a>Примечания

Для вспомогательной функции используется соглашение о вызове `__stdcall`. Тип возвращаемого значения неважен, поэтому используется тип FARPROC. Для этой функции используется компоновка C.

Возвращаемое значение вспомогательной подпрограммы загрузки с задержкой должно быть сохранено в переданном указателе на функцию, если только подпрограмма не должна использоваться в качестве обработчика уведомлений. В этом случае за поиск необходимого возвращаемого указателя на функцию отвечает пользовательский код. Затем код преобразователя, создаваемый компоновщиком, принимает это возвращаемое значение в качестве действительной цели импорта и переходит непосредственно к ней.

## <a name="sample"></a>Пример

В приведенном ниже примере показано, как реализовать простейшую функцию-обработчик.

```C
FARPROC WINAPI delayHook(unsigned dliNotify, PDelayLoadInfo pdli)
{
    switch (dliNotify) {
        case dliStartProcessing :

            // If you want to return control to the helper, return 0.
            // Otherwise, return a pointer to a FARPROC helper function
            // that will be used instead, thereby bypassing the rest
            // of the helper.

            break;

        case dliNotePreLoadLibrary :

            // If you want to return control to the helper, return 0.
            // Otherwise, return your own HMODULE to be used by the
            // helper instead of having it call LoadLibrary itself.

            break;

        case dliNotePreGetProcAddress :

            // If you want to return control to the helper, return 0.
            // If you choose you may supply your own FARPROC function
            // address and bypass the helper's call to GetProcAddress.

            break;

        case dliFailLoadLib :

            // LoadLibrary failed.
            // If you don't want to handle this failure yourself, return 0.
            // In this case the helper will raise an exception
            // (ERROR_MOD_NOT_FOUND) and exit.
            // If you want to handle the failure by loading an alternate
            // DLL (for example), then return the HMODULE for
            // the alternate DLL. The helper will continue execution with
            // this alternate DLL and attempt to find the
            // requested entrypoint via GetProcAddress.

            break;

        case dliFailGetProc :

            // GetProcAddress failed.
            // If you don't want to handle this failure yourself, return 0.
            // In this case the helper will raise an exception
            // (ERROR_PROC_NOT_FOUND) and exit.
            // If you choose you may handle the failure by returning
            // an alternate FARPROC function address.

            break;

        case dliNoteEndProcessing :

            // This notification is called after all processing is done.
            // There is no opportunity for modifying the helper's behavior
            // at this point except by longjmp()/throw()/RaiseException.
            // No return value is processed.

            break;

        default :

            return NULL;
    }

    return NULL;
}

/*
and then at global scope somewhere
PfnDliHook __pfnDliNotifyHook2 = delayHook;
*/
```

## <a name="see-also"></a>См. также

[Понятие вспомогательной функции](../../build/reference/understanding-the-helper-function.md)