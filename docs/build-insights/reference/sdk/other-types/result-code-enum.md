---
title: RESULT_CODE enum
description: SDK Build Insights sDK RESULT_CODE ссылку.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RESULT_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 62874e176c3f3e8f9df1ca64e7b593b7a0ef5c01
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323624"
---
# <a name="result_code-enum"></a>RESULT_CODE enum

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

В `RESULT_CODE` описании описаны условия успеха и неудачи.

## <a name="members"></a>Участники

| name | Значение | Описание |
|--|--|--|
| `RESULT_CODE_SUCCESS` | 0 (0x0000000000) | Операция выполнена успешно. |
| `RESULT_CODE_FAILURE_ANALYSIS_ERROR` | 1 (0x00000001) | Одна из функций обратного вызова `CALLBACK_CODE_ANALYSIS_FAILURE` в [ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) или [RELOG_DESCRIPTOR](relog-descriptor-struct.md) вернула значение. Это значение является членом [CALLBACK_CODE](callback-code-enum.md) enum. |
| `RESULT_CODE_FAILURE_CANCELLED` | 2 (0x00000002) | Одна из функций обратного вызова `CALLBACK_CODE_ANALYSIS_CANCEL` в [ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) или [RELOG_DESCRIPTOR](relog-descriptor-struct.md) вернула значение. Это значение является членом [CALLBACK_CODE](callback-code-enum.md) enum. |
| `RESULT_CODE_FAILURE_INVALID_INPUT_LOG_FILE` | 3 (0x00000003) | Отслеживание ввода событий для отслеживания Windows (ETW) является недействительным. |
| `RESULT_CODE_FAILURE_INVALID_OUTPUT_LOG_FILE` | 4 (0x000000004) | Указанный след выхода ETW является недействительным. |
| `RESULT_CODE_FAILURE_MISSING_ANALYSIS_CALLBACK` | 5 (0x000000005) | Структура [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) не была правильно инициализирована. |
| `RESULT_CODE_FAILURE_MISSING_RELOG_CALLBACK` | 6 (0x000000006) | Структура [RELOG_CALLBACKS](relog-callbacks-struct.md) не была правильно инициализирована. |
| `RESULT_CODE_FAILURE_OPEN_INPUT_TRACE` | 7 (0x00000007) | Не удалось открыть входный след ETW. |
| `RESULT_CODE_FAILURE_PROCESS_TRACE` | 8 (0x000000008) | Ошибка произошла при обработке вхотоза ETW-трассы. |
| `RESULT_CODE_FAILURE_START_RELOGGER` | 9 (0x000000009) | При попытке запуска сеанса перезаписи произошла ошибка. |
| `RESULT_CODE_FAILURE_DROPPED_EVENTS` | 10 (0x00000000A) | Ввхотявный след ETW отсутствует важных событий. |
| `RESULT_CODE_FAILURE_UNSUPPORTED_OS` | 11 (0x00000000B) | Вы используете исследования сборки сс помощью неподдерживаемой версии Windows. |
| `RESULT_CODE_FAILURE_INVALID_TRACING_SESSION_NAME` | 12 (0x0000000C) | При условии, что имя сеанса является недействительным. |
| `RESULT_CODE_FAILURE_INSUFFICIENT_PRIVILEGES` | 13 (0x0000000D) | Эта операция требует привилегий администратора. |
| `RESULT_CODE_FAILURE_GENERATE_GUID` | 14 (0x00000000E) | Ошибка произошла при генерации GUID. |
| `RESULT_CODE_FAILURE_OBTAINING_TEMP_DIRECTORY` | 15 (0x00000000F) | Ошибка произошла при попытке определить временный путь каталога. |
| `RESULT_CODE_FAILURE_CREATE_TEMPORARY_DIRECTORY` | 16 (0x00000010) | Ошибка произошла при попытке создать временный каталог для запуска сеанса отслеживания. |
| `RESULT_CODE_FAILURE_START_SYSTEM_TRACE` | 17 (0x00000011) | При попытке запуска системного следа произошла ошибка. |
| `RESULT_CODE_FAILURE_START_MSVC_TRACE` | 18 (0x00000012) | При попытке запустить трассу MSVC произошла ошибка. |
| `RESULT_CODE_FAILURE_STOP_MSVC_TRACE` | 19 (0x00000013) | Ошибка произошла при попытке остановить след MSVC. |
| `RESULT_CODE_FAILURE_STOP_SYSTEM_TRACE` | 20 (0x00000014) | При попытке запуска системного следа произошла ошибка. |
| `RESULT_CODE_FAILURE_SESSION_DIRECTORY_RESOLUTION` | 21 (0x00000015) | След был остановлен, но временный каталог сеанса отслеживания не может быть найден. |
| `RESULT_CODE_FAILURE_MSVC_TRACE_FILE_NOT_FOUND` | 22 (0x00000016) | Файл трассировки для остановки трассы MSVC не может быть найден. |
| `RESULT_CODE_FAILURE_MERGE_TRACES` | 23 (0x00000017) | Ошибка произошла при слиянии следов с помощью управления кернелом. |
| `RESULT_CODE_FAILURE_UNKNOWN_ERROR` | 24 (0x00000018) | Произошла неизвестная ошибка. |

::: moniker-end
