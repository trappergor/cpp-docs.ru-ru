---
title: Встроенные объекты ARM64
description: Список внутренних данных ARM64, поддерживаемых компилятором Microsoft C е.
f1_keywords:
- __break
- __addx18byte
- __addx18word
- __addx18dword
- __addx18qword
- __cas8
- __cas16
- __cas32
- __cas64
- __casa8
- __casa16
- __casa32
- __casa64
- __casl8
- __casl16
- __casl32
- __casl64
- __casal8
- __casal16
- __casal32
- __casal64
- __crc32b
- __crc32h
- __crc32w
- __crc32d
- __crc32cb
- __crc32ch
- __crc32cw
- __crc32cd
- __getReg
- __getRegFp
- __getCallerReg
- __getCallerRegFp
- __hlt
- __incx18byte
- __incx18word
- __incx18dword
- __incx18qword
- __ldar8
- __ldar16
- __ldar32
- __ldar64
- __ldapr8
- __ldapr16
- __ldapr32
- __ldapr64
- __prefetch2
- __readx18byte
- __readx18word
- __readx18dword
- __readx18qword
- __setReg
- __setRegFp
- __setCallerReg
- __setCallerRegFp
- __stlr8
- __stlr16
- __stlr32
- __stlr64
- __swp8
- __swp16
- __swp32
- __swp64
- __swpa8
- __swpa16
- __swpa32
- __swpa64
- __swpl8
- __swpl16
- __swpl32
- __swpl64
- __swpal8
- __swpal16
- __swpal32
- __swpal64
- __sys
- __svc
- __writex18byte
- __writex18word
- __writex18dword
- __writex18qword
author: sigatrev
ms.author: magardn
ms.date: 11/14/2019
ms.openlocfilehash: 196518439445824ddf5a7a841b30eb816251ba60
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368206"
---
# <a name="arm64-intrinsics"></a>Встроенные объекты ARM64

Компилятор Microsoft C '(MSVC) делает следующие внутренностями доступными на архитектуре ARM64. Для получения дополнительной информации о ARM можно ознакомиться в разделах «Инструменты архитектуры и разработки программного обеспечения» на веб-сайте [документации разработчиков ARM.](https://developer.arm.com/docs)

## <a name="neon"></a><a name="top"></a>Неоновые

Векторная инструкция NEON, устанавливаемые расширения для ARM64, обеспечивает возможности единой инструкции multiple Data (SIMD). Они напоминают те, в MMX и SSE векторные инструкции наборы, которые являются общими для x86 и x64 архитектуры процессоров.

NeON внутреннозависимости поддерживаются, как это предусмотрено в файле заголовка *arm64_neon.h*. Поддержка MSVC для внутреннозависимостей NEON напоминает компилятор ARM64, который задокументирован в справке [ARM NEON](https://static.docs.arm.com/ihi0073/c/IHI0073C_arm_neon_intrinsics_ref.pdf) на веб-сайте ARM Infocenter.

## <a name="arm64-specific-intrinsics-listing"></a><a name="A"></a>ARM64-специфические внутренностя листинг

|Имя функции|Инструкция|Прототип функции|
|-------------------|-----------------|------------------------|
|__break|Brk|пустота __break (int)|
|__addx18byte||аннулированная __addx18byte (неподписанный длинный, неподписанный символ)|
|__addx18word||пустота __addx18word (неподписанный длинный, неподписанный короткий)|
|__addx18dword||недействительный __addx18dword (неподписанный длинный, неподписанный длинный)|
|__addx18qword||недействительный __addx18qword (неподписанный длинный, неподписанный __int64)|
|__cas8|CASB|неподписанные __cas8 __int8 (неподписанные __int8 летучие _Target, неподписанные _Comp __int8, неподписанные __int8 _Value)|
|__cas16|Наличными|неподписанные __int16 __cas16 (неподписанные __int16 летучие _Target, неподписанные _Comp __int16, неподписанные __int16 _Value)|
|__cas32|CAS|неподписанные __int32 __cas32 (неподписанные __int32 летучие _Target, неподписанные _Comp __int32, неподписанные __int32 _Value)|
|__cas64|CAS|неподписанные __cas64 __int64 (неподписанные __int64 летучие _Target, неподписанные __int64 _Comp, неподписанные __int64 _Value)|
|__casa8|КАСАБ|неподписанные __casa8 __int8 (неподписанные __int8 летучие _Target, неподписанные _Comp __int8, неподписанные __int8 _Value)|
|__casa16|КАСА|неподписанные __int16 __casa16 (неподписанные __int16 летучие _Target, неподписанные __int16 _Comp, неподписанные __int16 _Value)|
|__casa32|Casa|неподписанные __int32 __casa32 (неподписанные __int32 летучие _Target, неподписанные __int32 _Comp, неподписанные __int32 _Value)|
|__casa64|Casa|неподписанные __casa64 __int64 (неподписанные __int64 летучие _Target, неподписанные __int64 _Comp, неподписанные __int64 _Value)|
|__casl8|КАСЛБ|неподписанные __casl8 __int8 (неподписанные __int8 летучие _Target, неподписанные _Comp __int8, неподписанные __int8 _Value)|
|__casl16|CASLH|неподписанные __casl16 __int16 (неподписанные __int16 летучие _Target, неподписанные _Comp __int16, неподписанные __int16 _Value)|
|__casl32|CASL|неподписанные __casl32 __int32 (неподписанные __int32 летучие _Target, неподписанные _Comp __int32, неподписанные __int32 _Value)|
|__casl64|CASL|неподписанные __casl64 __int64 (неподписанные __int64 летучие _Target, неподписанные _Comp __int64, неподписанные __int64 _Value)|
|__casal8|CASALB|неподписанные __int8 __casal8 (неподписанные __int8 летучие _Target, неподписанные _Comp __int8, неподписанные __int8 _Value)|
|__casal16|КАЗАЛХ|неподписанные __casal16 __int16 (неподписанные __int16 летучие _Target, неподписанные __int16 _Comp, неподписанные __int16 _Value)|
|__casal32|Casal|неподписанные __int32 __casal32 (неподписанные __int32 летучие _Target, неподписанные _Comp __int32, неподписанные __int32 _Value)|
|__casal64|Casal|неподписанные __int64 __casal64 (неподписанные __int64 летучие _Target, неподписанные _Comp __int64, неподписанные __int64 _Value)|
|__crc32b|CRC32B|неподписанные __crc32b __int32 (неподписанные __int32, неподписанные __int32)|
|__crc32h|CRC32H|неподписанные __crc32h __int32 (неподписанные __int32, неподписанные __int32)|
|__crc32w|CRC32W|неподписанные __crc32w __int32 (неподписанные __int32, неподписанные __int32)|
|__crc32d|CRC32X|неподписанные __crc32d __int32 (неподписанные __int32, неподписанные __int64)|
|__crc32cb|CRC32CB|неподписанные __crc32cb __int32 (неподписанные __int32, неподписанные __int32)|
|__crc32ch|CRC32CH|неподписанные __crc32ch __int32 (неподписанные __int32, неподписанные __int32)|
|__crc32cw|CRC32CW|неподписанные __crc32cw __int32 (неподписанные __int32, неподписанные __int32)|
|__crc32cd|CRC32CX|неподписанные __crc32cd __int32 (неподписанные __int32, неподписанные __int64)|
|__dmb|DMB|void __dmb(unsigned int `_Type`)<br /><br /> Вставляет операцию барьера памяти в поток инструкций. Параметр `_Type` указывает тип ограничения, которое накладывает барьер.<br /><br /> Для получения дополнительной информации о видах ограничений, которые могут быть введены, [см.](#BarrierRestrictions)|
|__dsb|DSB|void __dsb(unsigned int _Type)<br /><br /> Вставляет операцию барьера памяти в поток инструкций. Параметр `_Type` указывает тип ограничения, которое накладывает барьер.<br /><br /> Для получения дополнительной информации о видах ограничений, которые могут быть введены, [см.](#BarrierRestrictions)|
|__isb|ISB|void __isb(unsigned int _Type)<br /><br /> Вставляет операцию барьера памяти в поток инструкций. Параметр `_Type` указывает тип ограничения, которое накладывает барьер.<br /><br /> Для получения дополнительной информации о видах ограничений, которые могут быть введены, [см.](#BarrierRestrictions)|
|__getReg||неподписанные __getReg __int64 (int)|
|__getRegFp||двойное __getRegFp (int)|
|__getCallerReg||неподписанные __int64 __getCallerReg (int)|
|__getCallerRegFp||двойной __getCallerRegFp (int)|
|__hvc|HVC|unsigned int __hvc(unsigned int, ...)|
|__hlt|Hlt|int __hlt (неподписанный Int, ...)|
|__incx18byte||недействительный __incx18byte (неподписанный длинный)|
|__incx18word||аннулированная __incx18word (неподписанная длинная)|
|__incx18dword||пустота __incx18dword (неподписанный длинный)|
|__incx18qword||недействительный __incx18qword (неподписанный длинный)|
|__iso_volatile_load16||__int16 \__iso_volatile_load16 (конст летучих \__int16) \*<br /><br /> Для получения дополнительной [информации,](#IsoVolatileLoadStore)см __iso_volatile_load / хранить внутреннюю .|
|__iso_volatile_load32||__int32 \__iso_volatile_load32 (конст летучих \__int32) \*<br /><br /> Для получения дополнительной [информации,](#IsoVolatileLoadStore)см __iso_volatile_load / хранить внутреннюю .|
|__iso_volatile_load64||__int64 \__iso_volatile_load64 (конст летучих \__int64) \*<br /><br /> Для получения дополнительной [информации,](#IsoVolatileLoadStore)см __iso_volatile_load / хранить внутреннюю .|
|__iso_volatile_load8||__int8 \__iso_volatile_load8 (конст летучих \__int8) \*<br /><br /> Для получения дополнительной [информации,](#IsoVolatileLoadStore)см __iso_volatile_load / хранить внутреннюю .|
|__iso_volatile_store16||недействительный \___iso_volatile_store16 \* \_(летучие _int16, _int16)<br /><br /> Для получения дополнительной [информации,](#IsoVolatileLoadStore)см __iso_volatile_load / хранить внутреннюю .|
|__iso_volatile_store32||недействительные \___iso_volatile_store32 \* \_(летучие _int32, _int32)<br /><br /> Для получения дополнительной [информации,](#IsoVolatileLoadStore)см __iso_volatile_load / хранить внутреннюю .|
|__iso_volatile_store64||пустота __iso_volatile_store64 \_ \*(летучие _int64, \__int64)<br /><br /> Для получения дополнительной [информации,](#IsoVolatileLoadStore)см __iso_volatile_load / хранить внутреннюю .|
|__iso_volatile_store8||пустота __iso_volatile_store8 \_ \*(летучие _int8, \__int8)<br /><br /> Для получения дополнительной [информации,](#IsoVolatileLoadStore)см __iso_volatile_load / хранить внутреннюю .|
|__ldar8|LDARB|неподписанные __ldar8 __int8 (неподписанные __int8 летучие _Target)|
|__ldar16|ЛДАРХ|неподписанные __ldar16 __int16 (неподписанные __int16 летучие _Target)|
|__ldar32|LDAR|неподписанные __ldar32 __int32 (неподписанные __int32 летучие _Target)|
|__ldar64|LDAR|неподписанные __ldar64 __int64 (неподписанные __int64 летучие) _Target)|
|__ldapr8|ЛДАПРОБ|неподписанные __ldapr8 __int8 (неподписанные __int8 летучие) _Target)|
|__ldapr16|ЛДАПР|неподписанные __ldapr16 __int16 (неподписанные __int16 летучие) _Target)|
|__ldapr32|LDAPR|неподписанные __int32 __ldapr32 (неподписанные __int32 летучие) _Target)|
|__ldapr64|LDAPR|неподписанные __ldapr64 __int64 (неподписанные __int64 летучие) _Target)|
|__mulh||\__int64 __mulh\_(_int64, \__int64)|
|__prefetch|PRFM|пустота \___cdecl _prefetch \*(конст непусто )<br /><br /> Обеспечивает `PRFM` подсказку памяти с `PLDL1KEEP` помощью операции prefetch для системы, что память на или вблизи указанного адреса могут быть доступны в ближайшее время. В некоторых системах можно оптимизировать шаблон доступа к памяти для повышения производительности во время выполнения. Тем не менее, с точки зрения языка C++, функция на имеет видимой активности и вообще может не предпринимать никаких действий.|
|__prefetch2|PRFM|пустота \___cdecl _prefetch \*(конст недействительным , uint8_t prfop)<br /><br /> Обеспечивает `PRFM` подсказку памяти с предоставленной операцией prefetch к системе, что память на или вблизи указанного адреса могут быть доступны в ближайшее время. В некоторых системах можно оптимизировать шаблон доступа к памяти для повышения производительности во время выполнения. Тем не менее, с точки зрения языка C++, функция на имеет видимой активности и вообще может не предпринимать никаких действий.|
|__readx18byte||неподписанный символ __readx18byte (неподписанный длинный)|
|__readx18word||неподписанные короткие __readx18word (неподписанные длинные)|
|__readx18dword||неподписанный длинный __readx18dword (неподписанный длинный)|
|__readx18qword||неподписанные __readx18qword __int64 (неподписанные длинные)|
|__setReg||недействительный __setReg (int, неподписанный __int64)|
|__setRegFp||пустота __setRegFp (int, двойной)|
|__setCallerReg||пустота __setCallerReg (int, неподписанные __int64)|
|__setCallerRegFp||пустота __setCallerRegFp (int, двойной)|
|__sev|SEV|void __sev(void)|
|__static_assert||пустота __static_assert (int, \*const char)|
|__stlr8|STLRB|недействительный __stlr8 (неподписанный __int8 летучий _Target, неподписанный __int8 _Value)|
|__stlr16|STLRH|недействительный __stlr16 (неподписанный __int16 летучий _Target, неподписанный __int16 _Value)|
|__stlr32|STLR|недействительный __stlr32 (неподписанный __int32 летучий _Target, неподписанный __int32 _Value)|
|__stlr64|STLR|недействительный __stlr64 (неподписанный __int64 летучий _Target, неподписанный __int64 _Value)|
|__swp8|SWPB|неподписанные __swp8 __int8 (неподписанные __int8 летучие _Target, неподписанные __int8 _Value)|
|__swp16|SWPH|неподписанные __swp16 __int16 (неподписанные __int16 летучие _Target, неподписанные __int16 _Value)|
|__swp32|Swp|неподписанные __swp32 __int32 (неподписанные __int32 летучие _Target, неподписанные __int32 _Value)|
|__swp64|Swp|неподписанные __swp64 __int64 (неподписанные __int64 летучие _Target, неподписанные __int64 _Value)|
|__swpa8|SWPAB|неподписанные __swpa8 __int8 (неподписанные __int8 летучие _Target, неподписанные __int8 _Value)|
|__swpa16|SWPAH|неподписанные __swpa16 __int16 (неподписанные __int16 летучие _Target, неподписанные __int16 _Value)|
|__swpa32|SWPA|неподписанные __swpa32 __int32 (неподписанные __int32 летучие _Target, неподписанные _Value __int32)|
|__swpa64|SWPA|неподписанные __swpa64 __int64 (неподписанные __int64 летучие _Target, неподписанные __int64 _Value)|
|__swpl8|SWPLB|неподписанные __swpl8 __int8 (неподписанные __int8 летучие _Target, неподписанные __int8 _Value)|
|__swpl16|SWPLH|неподписанные __swpl16 __int16 (неподписанные __int16 летучие _Target, неподписанные __int16 _Value)|
|__swpl32|SWPL|неподписанные __swpl32 __int32 (неподписанные __int32 летучие _Target, неподписанные __int32 _Value)|
|__swpl64|SWPL|неподписанные __swpl64 __int64 (неподписанные __int64 летучие _Target, неподписанные _Value __int64)|
|__swpal8|SWPALB|неподписанные __int8 __swpal8 (неподписанные __int8 летучие _Target, неподписанные __int8 _Value)|
|__swpal16|SWPALH|неподписанные __int16 __swpal16 (неподписанные __int16 летучие _Target, неподписанные __int16 _Value)|
|__swpal32|SWPAL|неподписанные __swpal32 __int32 (неподписанные __int32 летучие _Target, неподписанные __int32 _Value)|
|__swpal64|SWPAL|неподписанные __swpal64 __int64 (неподписанные __int64 летучие _Target, неподписанные __int64 _Value)|
|__sys|Sys|неподписанный int __sys (int, __int64)|
|__svc|SVC|неподписанный int __svc (неподписанный Int, ...)|
|__wfe|WFE|void __wfe(void)|
|__wfi|WFI|void __wfi(void)|
|__writex18byte||пустота __writex18byte (неподписанный длинный, неподписанный символ)|
|__writex18word||пустота __writex18word (неподписанный длинный, неподписанный короткий)|
|__writex18dword||недействительный __writex18dword (неподписанный длинный, неподписанный длинный)|
|__writex18qword||недействительный __writex18qword (неподписанный длинный, неподписанный __int64)|
|__umulh||неподписанные \___umulh _int64 \_(неподписанные _int64, неподписанные \__int64)|
|_CopyDoubleFromInt64||двойной\__CopyDoubleFromInt64 (_int64)|
|_CopyFloatFromInt32||_CopyFloatFromInt32 поплавка (_int32)\_|
|_CopyInt32FromFloat||__int32 _CopyInt32FromFloat(float)|
|_CopyInt64FromDouble||__int64 _CopyInt64FromDouble(double)|
|_CountLeadingOnes||unsigned int _CountLeadingOnes(unsigned long)|
|_CountLeadingOnes64||неподписанный int _CountLeadingOnes64 \_(неподписанный _int64)|
|_CountLeadingSigns||unsigned int _CountLeadingSigns(long)|
|_CountLeadingSigns64||неподписанный int\__CountLeadingSigns64 (_int64)|
|_CountLeadingZeros||unsigned int _CountLeadingZeros(unsigned long)|
|_CountLeadingZeros64||неподписанный int _CountLeadingZeros64 \_(неподписанный _int64)|
|_ReadStatusReg|MRS|\__int64 _ReadStatusReg (int)|
|_WriteStatusReg|MSR|пустота _WriteStatusReg (int, \__int64)|

Возвращение[на вершину](#top)

### <a name="memory-barrier-restrictions"></a><a name="BarrierRestrictions"></a>Ограничения барьера памяти

Внутренние функции `__dmb` (барьер памяти `__dsb` данных), (барьер синхронизации `__isb` данных) и (барьер синхронизации инструкций) используют следующие предопределенные значения для определения ограничения барьера памяти с точки зрения домена общего доступа и типа доступа, который зависит от операции.

|Restriction Value|Описание|
|-----------------------|-----------------|
|_ARM64_BARRIER_SY|Полная система, операции чтения и записи.|
|_ARM64_BARRIER_ST|Полная система, только запись.|
|_ARM64_BARRIER_LD|Полная система, только читать.|
|_ARM64_BARRIER_ISH|Внутренний общий, чтение и запись.|
|_ARM64_BARRIER_ISHST|Внутренний общий, только запись.|
|_ARM64_BARRIER_ISHLD|Внутренний sharable, читать только.|
|_ARM64_BARRIER_NSH|Не общий, чтение и запись.|
|_ARM64_BARRIER_NSHST|Не общий, только запись.|
|_ARM64_BARRIER_NSHLD|Не-шарный, только читать.|
|_ARM64_BARRIER_OSH|Внешний общий, чтение и запись.|
|_ARM64_BARRIER_OSHST|Внешний общий, только запись.|
|_ARM64_BARRIER_OSHLD|Внешний sharable, читать только.|

Для `__isb` внутренненативой, единственное ограничение, которое в настоящее время действует, _ARM64_BARRIER_SY; все остальные значения зарезервированы архитектурой.

### <a name="__iso_volatile_loadstore-intrinsics"></a><a name="IsoVolatileLoadStore"></a>__iso_volatile_load/магазин внутренностих

Эти внутренние функции явно выполняют нагрузки и магазины, которые не подлежат оптимизации компилятора.

```C
__int16 __iso_volatile_load16(const volatile __int16 * Location);
__int32 __iso_volatile_load32(const volatile __int32 * Location);
__int64 __iso_volatile_load64(const volatile __int64 * Location);
__int8 __iso_volatile_load8(const volatile __int8 * Location);

void __iso_volatile_store16(volatile __int16 * Location, __int16 Value);
void __iso_volatile_store32(volatile __int32 * Location, __int32 Value);
void __iso_volatile_store64(volatile __int64 * Location, __int64 Value);
void __iso_volatile_store8(volatile __int8 * Location, __int8 Value);
```

#### <a name="parameters"></a>Параметры

*Расположение*\
Адрес области памяти для чтения или записи.

*Значение*\
Значение для записи в указанное местоположение памяти (только для хранения внутренних хранилиров).

#### <a name="return-value-load-intrinsics-only"></a>Значение возврата (нагрузка только внутренняя)

Значение местоположения памяти, указанное *местоположением*.

#### <a name="remarks"></a>Remarks

Вы можете `__iso_volatile_load8/16/32/64` использовать `__iso_volatile_store8/16/32/64` и внутреннюю часть для явного выполнения доступа к памяти, которые не подлежат оптимизации компилятора. Компилятор не может удалить, синтезировать или изменить относительный порядок этих операций. Тем не менее, он не генерирует неявные барьеры аппаратной памяти. Таким образом оборудование по-прежнему может переупорядочить возникающие операции доступа к памяти между несколькими потоками. Точнее, эти внутренностия эквивалентны следующим выражениям, составленным под **/volatile:iso**.

```cpp
int a = __iso_volatile_load32(p);    // equivalent to: int a = *(const volatile __int32*)p;
__iso_volatile_store32(p, a);        // equivalent to: *(volatile __int32*)p = a;
```

Обратите внимание, что встроенные функции принимают временные указатели для размещения временных переменных. Тем не менее, нет никаких требований или рекомендаций использовать летучие указатели в качестве аргументов. Семантика этих операций точно такая же, если используется обычный, нелетучий тип.

Для получения дополнительной информации о **/летучих:iso** командной строке аргумент, [см/ летучих (летучих ключевых слов интерпретации)](../build/reference/volatile-volatile-keyword-interpretation.md).

## <a name="arm64-support-for-intrinsics-from-other-architectures"></a><a name="I"></a>Поддержка ARM64 для внутренностих других архитектур

В следующей таблице перечислены внутренняя часть других архитектур, которая поддерживается на платформах ARM64. В тех случаях, когда поведение неотъемлемых на ARM64 отличается от его поведения на других аппаратных архитектурах, отмечаются дополнительные детали.

|Имя функции|Прототип функции|
|-------------------|------------------------|
|__assume|void __assume(int)|
|__code_seg|пустота __code_seg (конст-символ \*)|
|__debugbreak|пустота \___cdecl _debugbreak (пустота)|
|__fastfail|__declspec (безвозврат) \_недействительным _fastfail (неподписанный int)|
|__nop|void __nop(void)|
|__yield|недействительным __yield (недействительным) **Примечание:** На платформах ARM64, эта функция генерирует инструкцию YIELD. Эта инструкция указывает на то, что поток выполняет задачу, которая может быть временно приостановлена от выполнения, например, спинлок, не влияя на программу. Это позволяет процессору выполнять другие задачи во время циклов выполнения, которые в противном случае были бы потрачены впустую.|
|_AddressOfReturnAddress|пустота \* _AddressOfReturnAddress (пустота)|
|_BitScanForward|неподписанный _BitScanForward char \* (неподписанный длинный _Index, неподписанный длинный _Mask)|
|_BitScanForward64|неподписанный _BitScanForward64 символа \* (неподписанный длинный _Index, неподписанный __int64 _Mask)|
|_BitScanReverse|неподписанный _BitScanReverse char \* (неподписанный длинный _Index, неподписанный длинный _Mask)|
|_BitScanReverse64|неподписанные _BitScanReverse64 char \* (неподписанные длинные _Index, неподписанные __int64 _Mask)|
|_bittest|неподписанный _bittest (длинный \*const , длинный)|
|_bittest64|неподписанный символ _bittest64 \*(__int64 конст , __int64)|
|_bittestandcomplement|неподписанный символ \*_bittestandcomplement (длинный, длинный)|
|_bittestandcomplement64|неподписанный символ \*_bittestandcomplement64 (__int64, __int64)|
|_bittestandreset|неподписанный символ \*_bittestandreset (длинный, длинный)|
|_bittestandreset64|неподписанные _bittestandreset64 \*(__int64, __int64)|
|_bittestandset|неподписанный символ \*_bittestandset (длинный, длинный)|
|_bittestandset64|неподписанные _bittestandset64 \*(__int64, __int64)|
|_byteswap_uint64|неподписанные \__byteswap_uint64 _cdecl \___int64 (неподписанные _int64)|
|_byteswap_ulong|unsigned long __cdecl _byteswap_ulong(unsigned long)|
|_byteswap_ushort|unsigned short __cdecl _byteswap_ushort(unsigned short)|
|_disable|пустота __cdecl _disable (пустой) **Примечание:** На платформах ARM64, эта функция генерирует инструкцию `MSR DAIFCLR,#2`; он доступен только в качестве неотъемлемого.|
|_enable|недействительным __cdecl _enable (недействительным) **Примечание:** На платформах ARM64, эта функция генерирует инструкцию `MSR DAIFSET,#2`; он доступен только в качестве неотъемлемого.|
|_lrotl|unsigned long __cdecl _lrotl(unsigned long, int)|
|_lrotr|unsigned long __cdecl _lrotr(unsigned long, int)|
|_ReadBarrier|void _ReadBarrier(void)|
|_ReadWriteBarrier|void _ReadWriteBarrier(void)|
|_ReturnAddress|пустота \* _ReturnAddress (пустоты)|
|_rotl|unsigned int __cdecl _rotl(unsigned int _Value, int _Shift)|
|_rotl16|unsigned short _rotl16(unsigned short _Value, unsigned char _Shift)|
|_rotl64|неподписанные \___int64 _cdecl \__rotl64 (неподписанные _int64 _Value, _Shift)|
|_rotl8|unsigned char _rotl8(unsigned char _Value, unsigned char _Shift)|
|_rotr|unsigned int __cdecl _rotr(unsigned int _Value, int _Shift)|
|_rotr16|unsigned short _rotr16(unsigned short _Value, unsigned char _Shift)|
|_rotr64|неподписанные \___int64 _cdecl \__rotr64 (неподписанные _Value _int64, _Shift)|
|_rotr8|unsigned char _rotr8(unsigned char _Value, unsigned char _Shift)|
|_setjmpex|int __cdecl _setjmpex(jmp_buf)|
|_WriteBarrier|void _WriteBarrier(void)|

Возвращение[на вершину](#top)

## <a name="interlocked-intrinsics"></a>Взаимосвязанные внутренностя

Блокирующие встроенные функции представляют собой набор встроенных функций, которые используются для выполнения атомарных операций чтения, изменения и записи. Некоторые из них общие для всех платформ. Они перечислены отдельно здесь, потому что есть большое количество из них. Поскольку их определения в основном излишни, легче думать о них в общих чертах. Их имена можно использовать для понимания точного поведения.

В следующей таблице кратко излагается поддержка ARM64 не-биттест взаимосвязанных внутренностей. Каждая ячейка в таблице соответствует имени, полученном путем добавления имени операции в самой левой ячейке строки к имени типа в самой верхней ячейке столбца для `_Interlocked`. Например, ячейка на пересечении `Xor` ряда `8` и столбца соответствует `_InterlockedXor8` и полностью поддерживается. Основные поддерживаемые функции предоставляют следующие дополнительные суффиксы: `_acq`, `_rel` и `_nf`. Суффикс `_acq` указывает «получить» семантику и суффикс `_rel` указывает «освободить» семантику. Суффикс `_nf` «нет забора» является уникальным для ARM и ARM64 и обсуждается в следующем разделе.

||8|16|32|64|128|P|
|-|-------|--------|--------|--------|-------|-------|
|Добавить|Отсутствуют|Отсутствуют|Полное|Полное|Отсутствуют|Отсутствуют|
|И|Полное|Полное|Полное|Полное|Отсутствуют|Отсутствуют|
|CompareExchange|Полное|Полное|Полное|Полное|Полное|Полное|
|Decrement|Отсутствуют|Полное|Полное|Полное|Отсутствуют|Отсутствуют|
|Exchange|Полное|Полное|Полное|Полное|Отсутствуют|Полное|
|ExchangeAdd|Полное|Полное|Полное|Полное|Отсутствуют|Отсутствуют|
|Приращение|Отсутствуют|Полное|Полное|Полное|Отсутствуют|Отсутствуют|
|Или|Полное|Полное|Полное|Полное|Отсутствуют|Отсутствуют|
|Xor|Полное|Полное|Полное|Полное|Отсутствуют|Отсутствуют|

Раздел:

- **Полный**: `_acq`поддерживает `_rel`равнину, и `_nf` формы.

- **Нет**: Не поддерживается

### <a name="_nf-no-fence-suffix"></a><a name="nf_suffix"></a>_nf (без забора) суффикс

Суффикс `_nf` «нет забора» указывает на то, что операция не ведет себя как какой-либо `_acq`барьер `_rel`памяти, в отличие от трех других форм (простые, и), которые все ведут себя как своего рода барьер. Одним из возможных видов использования `_nf` форм является поддержание счетчика статистики, который обновляется несколькими потоками одновременно, но значение которого в противном случае не используется в то время как несколько потоков исполняются.

### <a name="list-of-interlocked-intrinsics"></a>Список взаимосвязанных внутреннозависимостей

|Имя функции|Прототип функции|
|-------------------|------------------------|
|_InterlockedAdd|длинные _InterlockedAdd \*(длинные _volatile, длинные)|
|_InterlockedAdd64|__int64 _InterlockedAdd64\_(_int64 \_летучий, \*_int64)|
|_InterlockedAdd64_acq|__int64 _InterlockedAdd64_acq\_(_int64 \_летучие, \*_int64)|
|_InterlockedAdd64_nf|__int64 _InterlockedAdd64_nf\_(_int64 \_летучие, \*_int64)|
|_InterlockedAdd64_rel|__int64 _InterlockedAdd64_rel\_(_int64 \_летучий, \*_int64)|
|_InterlockedAdd_acq|длинные _InterlockedAdd_acq \*(длинные летучие, длинные)|
|_InterlockedAdd_nf|длинные _InterlockedAdd_nf \*(длинные летучие, длинные)|
|_InterlockedAdd_rel|длинные _InterlockedAdd_rel \*(длинные летучие, длинные)|
|_InterlockedAnd|долго _InterlockedAnd (длинный летучий, \*длинный)|
|_InterlockedAnd16|короткий _InterlockedAnd16 \*(короткий летучих, короткий)|
|_InterlockedAnd16_acq|короткий _InterlockedAnd16_acq \*(короткий летучих, короткий)|
|_InterlockedAnd16_nf|короткие _InterlockedAnd16_nf \*(короткие летучие, короткие)|
|_InterlockedAnd16_rel|короткие _InterlockedAnd16_rel \*(короткие летучие, короткие)|
|_InterlockedAnd64|__int64 _InterlockedAnd64\_(_int64 \_летучие, \*_int64)|
|_InterlockedAnd64_acq|__int64 _InterlockedAnd64_acq\_(_int64 \_летучие, \*_int64)|
|_InterlockedAnd64_nf|__int64 _InterlockedAnd64_nf\_(_int64 \_летучие, \*_int64)|
|_InterlockedAnd64_rel|_InterlockedAnd64_rel __int64\_(_int64 \_летучий, \*_int64)|
|_InterlockedAnd8|char _InterlockedAnd8 (char volatile, \*char)|
|_InterlockedAnd8_acq|char _InterlockedAnd8_acq (char volatile, \*char)|
|_InterlockedAnd8_nf|char _InterlockedAnd8_nf (char volatile, \*char)|
|_InterlockedAnd8_rel|char _InterlockedAnd8_rel (char volatile, \*char)|
|_InterlockedAnd_acq|длинные _InterlockedAnd_acq \*(длинные летучие, длинные)|
|_InterlockedAnd_nf|долгий _InterlockedAnd_nf \*(длинный летучий, длинный)|
|_InterlockedAnd_rel|длинные _InterlockedAnd_rel \*(длинные летучие, длинные)|
|_InterlockedCompareExchange|длинные __cdecl _InterlockedCompareExchange \*(длинные летучие, длинные, длинные)|
|_InterlockedCompareExchange_acq|длинные _InterlockedCompareExchange_acq \*(длинные летучие, длинные, длинные)|
|_InterlockedCompareExchange_nf|длинные _InterlockedCompareExchange_nf \*(длинные летучие, длинные, длинные)|
|_InterlockedCompareExchange_rel|длинные _InterlockedCompareExchange_rel \*(длинные летучие, длинные, длинные)|
|_InterlockedCompareExchange16|короткие _InterlockedCompareExchange16 \*(короткие летучие, короткие, короткие)|
|_InterlockedCompareExchange16_acq|короткие _InterlockedCompareExchange16_acq \*(короткие летучие, короткие, короткие)|
|_InterlockedCompareExchange16_nf|короткие _InterlockedCompareExchange16_nf \*(короткие летучие, короткие, короткие)|
|_InterlockedCompareExchange16_rel|короткие _InterlockedCompareExchange16_rel \*(короткие летучие, короткие, короткие)|
|_InterlockedCompareExchange64|__int64 _InterlockedCompareExchange64\_ \*(_int64 \_летучие, _int64, \__int64)|
|_InterlockedCompareExchange64_acq|__int64 _InterlockedCompareExchange64_acq\_ \*(_int64 \_летучие, _int64, \__int64)|
|_InterlockedCompareExchange64_nf|__int64 _InterlockedCompareExchange64_nf\_ \*(_int64 \_летучие, _int64, \__int64)|
|_InterlockedCompareExchange64_rel|__int64 _InterlockedCompareExchange64_rel\_ \*(_int64 \_летучие, _int64, \__int64)|
|_InterlockedCompareExchange8|char _InterlockedCompareExchange8 (char volatile, \*char, char)|
|_InterlockedCompareExchange8_acq|char _InterlockedCompareExchange8_acq (char летучий, \*char, char)|
|_InterlockedCompareExchange8_nf|char _InterlockedCompareExchange8_nf (char летучий, \*char, char)|
|_InterlockedCompareExchange8_rel|char _InterlockedCompareExchange8_rel (char летучий, \*char, char)|
|_InterlockedCompareExchangePointer|\* пустота _InterlockedCompareExchangePointer \* \*(пустота летучих , пустота \*, пустота \*)|
|_InterlockedCompareExchangePointer_acq|\* пустота _InterlockedCompareExchangePointer_acq \* \*(пустота летучих , пустота \*, пустота \*)|
|_InterlockedCompareExchangePointer_nf|\* пустота _InterlockedCompareExchangePointer_nf \* \*(пустота летучих , пустота \*, пустота \*)|
|_InterlockedCompareExchangePointer_rel|\* пустота _InterlockedCompareExchangePointer_rel \* \*(пустота летучих, пустота \*, пустота \*)|
|_InterlockedCompareExchange128|неподписанные _InterlockedCompareExchange128\_char \* ( \__int64 \_летучие \_ \* _Destination, _ExchangeHigh _int64, _int64 _ExchangeLow, _int64 _ComparandResult)|
|_InterlockedCompareExchange128_acq|неподписанные _InterlockedCompareExchange128_acq\_ \* (_int64 \_летучие \__Destination, \_ \* _ExchangeHigh _int64, _ExchangeLow _int64, _int64 _ComparandResult)|
|_InterlockedCompareExchange128_nf|неподписанные\__InterlockedCompareExchange128_nf(_int64 \* летучие _Destination, \__int64 _ExchangeHigh, \__int64 _ExchangeLow, \__int64 _ComparandResult) \*|
|_InterlockedCompareExchange128_rel|неподписанные\__InterlockedCompareExchange128_rel(_int64 \* летучие _Destination, \__int64 _ExchangeHigh, \__int64 _ExchangeLow, \__int64 \* _ComparandResult)|
|_InterlockedDecrement|долгий __cdecl _InterlockedDecrement \*(длинный летучих)|
|_InterlockedDecrement16|короткие _InterlockedDecrement16 \*(короткие летучие)|
|_InterlockedDecrement16_acq|короткие _InterlockedDecrement16_acq \*(короткие летучие)|
|_InterlockedDecrement16_nf|короткие _InterlockedDecrement16_nf \*(короткие летучие)|
|_InterlockedDecrement16_rel|короткие _InterlockedDecrement16_rel \*(короткие летучие)|
|_InterlockedDecrement64|__int64 _InterlockedDecrement64\_(_int64 летучие) \*|
|_InterlockedDecrement64_acq|__int64 _InterlockedDecrement64_acq\_(_int64 летучие) \*|
|_InterlockedDecrement64_nf|__int64 _InterlockedDecrement64_nf\_(_int64 летучие) \*|
|_InterlockedDecrement64_rel|__int64 _InterlockedDecrement64_rel\_(_int64 летучие) \*|
|_InterlockedDecrement_acq|длинные _InterlockedDecrement_acq \*(длинные летучие)|
|_InterlockedDecrement_nf|длинные _InterlockedDecrement_nf \*(длинные летучие)|
|_InterlockedDecrement_rel|долго _InterlockedDecrement_rel (длинный летучих) \*|
|_InterlockedExchange|длинные __cdecl _InterlockedExchange \* (длинные летучие _Target, длинные)|
|_InterlockedExchange_acq|длинные _InterlockedExchange_acq \* (длинные летучие _Target, длинные)|
|_InterlockedExchange_nf|длинные _InterlockedExchange_nf \* (длинные летучие _Target, длинные)|
|_InterlockedExchange_rel|длинные _InterlockedExchange_rel \* (длинные летучие _Target, длинные)|
|_InterlockedExchange16|короткие _InterlockedExchange16 \* (короткие летучие _Target, короткие)|
|_InterlockedExchange16_acq|короткие _InterlockedExchange16_acq \* (короткие летучие _Target, короткие)|
|_InterlockedExchange16_nf|короткие _InterlockedExchange16_nf \* (короткие летучие _Target, короткие)|
|_InterlockedExchange16_rel|короткие _InterlockedExchange16_rel \* (короткие летучие _Target, короткие)|
|_InterlockedExchange64|__int64 _InterlockedExchange64\_(_int64 \* \_летучие _Target, _int64)|
|_InterlockedExchange64_acq|__int64 _InterlockedExchange64_acq\_(_int64 \* \__Target, _int64)|
|_InterlockedExchange64_nf|__int64 _InterlockedExchange64_nf\_(_int64 \* \__Target, _int64)|
|_InterlockedExchange64_rel|__int64 _InterlockedExchange64_rel\_(_int64 \* \_летучие _Target, _int64)|
|_InterlockedExchange8|char _InterlockedExchange8 (char летучий \* _Target, char)|
|_InterlockedExchange8_acq|char _InterlockedExchange8_acq (char летучий \* _Target, char)|
|_InterlockedExchange8_nf|_InterlockedExchange8_nf (символ \* летучих _Target, char)|
|_InterlockedExchange8_rel|char _InterlockedExchange8_rel (char летучий \* _Target, char)|
|_InterlockedExchangeAdd|длинные _InterlockedExchangeAdd __cdecl \*(длинные летучие, длинные)|
|_InterlockedExchangeAdd16|короткие _InterlockedExchangeAdd16 \*(короткие летучие, короткие)|
|_InterlockedExchangeAdd16_acq|короткий _InterlockedExchangeAdd16_acq \*(короткий летучих, короткий)|
|_InterlockedExchangeAdd16_nf|короткие _InterlockedExchangeAdd16_nf \*(короткие летучие, короткие)|
|_InterlockedExchangeAdd16_rel|короткие _InterlockedExchangeAdd16_rel \*(короткие летучие, короткие)|
|_InterlockedExchangeAdd64|__int64 _InterlockedExchangeAdd64\_(_int64 \_летучие, \*_int64)|
|_InterlockedExchangeAdd64_acq|__int64 _InterlockedExchangeAdd64_acq\_(_int64 \_нестабильный, \*_int64)|
|_InterlockedExchangeAdd64_nf|__int64 _InterlockedExchangeAdd64_nf\_(_int64 \_летучие, \*_int64)|
|_InterlockedExchangeAdd64_rel|__int64 _InterlockedExchangeAdd64_rel\_(_int64 \_летучие, \*_int64)|
|_InterlockedExchangeAdd8|char _InterlockedExchangeAdd8 (char volatile, \*char)|
|_InterlockedExchangeAdd8_acq|char _InterlockedExchangeAdd8_acq (char volatile, \*char)|
|_InterlockedExchangeAdd8_nf|char _InterlockedExchangeAdd8_nf (char volatile, \*char)|
|_InterlockedExchangeAdd8_rel|char _InterlockedExchangeAdd8_rel (char volatile, \*char)|
|_InterlockedExchangeAdd_acq|длинные _InterlockedExchangeAdd_acq \*(длинные летучие, длинные)|
|_InterlockedExchangeAdd_nf|длинные _InterlockedExchangeAdd_nf \*(длинные летучие, длинные)|
|_InterlockedExchangeAdd_rel|долгий _InterlockedExchangeAdd_rel \*(длинный летучий, длинный)|
|_InterlockedExchangePointer|пустота \* _InterlockedExchangePointer \* \* (пустота \*летучих _Target, пустота )|
|_InterlockedExchangePointer_acq|недействительный \* \* _InterlockedExchangePointer_acq \* (пустота летучих _Target, пустота \*)|
|_InterlockedExchangePointer_nf|пустота \* _InterlockedExchangePointer_nf \* \* (пустота \*летучих _Target, пустота )|
|_InterlockedExchangePointer_rel|пустота \* _InterlockedExchangePointer_rel \* \* (пустота \*летучих _Target, пустота )|
|_InterlockedIncrement|долгий __cdecl _InterlockedIncrement \*(длинный летучих)|
|_InterlockedIncrement16|короткие _InterlockedIncrement16 \*(короткие летучие)|
|_InterlockedIncrement16_acq|короткие _InterlockedIncrement16_acq \*(короткие летучие)|
|_InterlockedIncrement16_nf|короткий _InterlockedIncrement16_nf \*(короткий летучих)|
|_InterlockedIncrement16_rel|короткие _InterlockedIncrement16_rel \*(короткие летучие)|
|_InterlockedIncrement64|__int64 _InterlockedIncrement64\_(_int64 летучие) \*|
|_InterlockedIncrement64_acq|__int64 _InterlockedIncrement64_acq\_(_int64 летучие) \*|
|_InterlockedIncrement64_nf|__int64 _InterlockedIncrement64_nf\_(_int64 летучие) \*|
|_InterlockedIncrement64_rel|__int64 _InterlockedIncrement64_rel\_(_int64 летучие) \*|
|_InterlockedIncrement_acq|длинные _InterlockedIncrement_acq \*(длинные летучие)|
|_InterlockedIncrement_nf|длинные _InterlockedIncrement_nf \*(длинные летучие)|
|_InterlockedIncrement_rel|длинные _InterlockedIncrement_rel \*(длинные летучие)|
|_InterlockedOr|длинные _InterlockedOr \*(длинные летучие, длинные)|
|_InterlockedOr16|короткий _InterlockedOr16 \*(короткий летучих, короткий)|
|_InterlockedOr16_acq|короткие _InterlockedOr16_acq \*(короткие летучие, короткие)|
|_InterlockedOr16_nf|короткий _InterlockedOr16_nf \*(короткий летучих, короткий)|
|_InterlockedOr16_rel|короткие _InterlockedOr16_rel \*(короткие летучие, короткие)|
|_InterlockedOr64|__int64 _InterlockedOr64\_(_int64 \_летучие, \*_int64)|
|_InterlockedOr64_acq|__int64 _InterlockedOr64_acq\_(_int64 \_летучие, \*_int64)|
|_InterlockedOr64_nf|__int64 _InterlockedOr64_nf\_(_int64 \_летучие, \*_int64)|
|_InterlockedOr64_rel|__int64 _InterlockedOr64_rel\_(_int64 \_летучий, \*_int64)|
|_InterlockedOr8|char _InterlockedOr8 (char volatile, \*char)|
|_InterlockedOr8_acq|char _InterlockedOr8_acq (char volatile, \*char)|
|_InterlockedOr8_nf|char _InterlockedOr8_nf (char volatile, \*char)|
|_InterlockedOr8_rel|char _InterlockedOr8_rel (char volatile, \*char)|
|_InterlockedOr_acq|длинные _InterlockedOr_acq \*(длинные летучие, длинные)|
|_InterlockedOr_nf|длинные _InterlockedOr_nf \*(длинные летучие, длинные)|
|_InterlockedOr_rel|долгий _InterlockedOr_rel \*(длинный летучий, длинный)|
|_InterlockedXor|длинные _InterlockedXor \*(длинные летучие, длинные)|
|_InterlockedXor16|короткие _InterlockedXor16 \*(короткие летучие, короткие)|
|_InterlockedXor16_acq|короткие _InterlockedXor16_acq \*(короткие летучие, короткие)|
|_InterlockedXor16_nf|короткий _InterlockedXor16_nf \*(короткий летучих, короткий)|
|_InterlockedXor16_rel|короткий _InterlockedXor16_rel \*(короткий летучих, короткий)|
|_InterlockedXor64|__int64 _InterlockedXor64\_(_int64 \_летучие, \*_int64)|
|_InterlockedXor64_acq|__int64 _InterlockedXor64_acq\_(_int64 \_летучие, \*_int64)|
|_InterlockedXor64_nf|__int64 _InterlockedXor64_nf\_(_int64 \_летучий, \*_int64)|
|_InterlockedXor64_rel|_InterlockedXor64_rel __int64\_(_int64 \_нестабильный, \*_int64)|
|_InterlockedXor8|char _InterlockedXor8 (char volatile, \*char)|
|_InterlockedXor8_acq|char _InterlockedXor8_acq (char volatile, \*char)|
|_InterlockedXor8_nf|char _InterlockedXor8_nf (char volatile, \*char)|
|_InterlockedXor8_rel|char _InterlockedXor8_rel (char volatile, \*char)|
|_InterlockedXor_acq|длинные _InterlockedXor_acq \*(длинные летучие, длинные)|
|_InterlockedXor_nf|длинные _InterlockedXor_nf \*(длинные летучие, длинные)|
|_InterlockedXor_rel|длинные _InterlockedXor_rel \*(длинные летучие, длинные)|

Возвращение[на вершину](#top)

### <a name="_interlockedbittest-intrinsics"></a>_interlockedbittest внутренняя часть

Простые взаимосвязанные детали теста intrinsics являются общими для всех платформ. ARM64 `_acq`добавляет `_rel`, `_nf` и варианты, которые просто изменить барьер семантики операции, как описано в [_nf (без забора) Суффикс](#nf_suffix) ранее в этой статье.

|Имя функции|Прототип функции|
|-------------------|------------------------|
|_interlockedbittestandreset|неподписанный символ _interlockedbittestandreset \*(длинный летучих , длинные)|
|_interlockedbittestandreset_acq|неподписанный _interlockedbittestandreset_acq char \*(длинный летучий, длинный)|
|_interlockedbittestandreset_nf|неподписанный символ _interlockedbittestandreset_nf \*(длинный летучих , длинные)|
|_interlockedbittestandreset_rel|неподписанный символ _interlockedbittestandreset_rel \*(длинный летучих , длинные)|
|_interlockedbittestandreset64|неподписанный _interlockedbittestandreset64 (__int64 летучий, \*__int64)|
|_interlockedbittestandreset64_acq|неподписанные _interlockedbittestandreset64_acq char \*(__int64 летучие, __int64)|
|_interlockedbittestandreset64_nf|неподписанный _interlockedbittestandreset64_nf char \*(__int64 летучий, __int64)|
|_interlockedbittestandreset64_rel|неподписанные _interlockedbittestandreset64_rel char \*(__int64 летучие, __int64)|
|_interlockedbittestandset|неподписанный _interlockedbittestandset char \*(длинный летучий, длинный)|
|_interlockedbittestandset_acq|неподписанный символ _interlockedbittestandset_acq \*(длинный летучих , длинные)|
|_interlockedbittestandset_nf|неподписанный символ _interlockedbittestandset_nf \*(длинный летучих , длинные)|
|_interlockedbittestandset_rel|неподписанный символ _interlockedbittestandset_rel \*(длинный летучих , длинные)|
|_interlockedbittestandset64|неподписанные _interlockedbittestandset64 char \*(__int64 летучие, __int64)|
|_interlockedbittestandset64_acq|неподписанный _interlockedbittestandset64_acq символа (__int64 летучий, \*__int64)|
|_interlockedbittestandset64_nf|неподписанный _interlockedbittestandset64_nf char \*(__int64 летучий, __int64)|
|_interlockedbittestandset64_rel|неподписанный _interlockedbittestandset64_rel char \*(__int64 летучий, __int64)|

Возвращение[на вершину](#top)

## <a name="see-also"></a>См. также раздел

[Компилятор внутренностих](../intrinsics/compiler-intrinsics.md)\
[Внутренняя часть ARM](arm-intrinsics.md)\
[Ссылка на сборку ARM](../assembler/arm/arm-assembler-reference.md)\
[Ссылка на язык СЗ](../cpp/cpp-language-reference.md)
