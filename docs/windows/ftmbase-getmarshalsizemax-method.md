---
title: Метод FtmBase::GetMarshalSizeMax | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase::GetMarshalSizeMax
dev_langs:
- C++
helpviewer_keywords:
- GetMarshalSizeMax method
ms.assetid: b416b1bf-c73e-45d5-abb8-04921c1a0c94
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c7976d0ea22a0bf6f59b020f892d407c4721b9a7
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39652361"
---
# <a name="ftmbasegetmarshalsizemax-method"></a>Метод FtmBase::GetMarshalSizeMax
Получите верхнюю границу на число байтов, необходимая для маршалинга заданный указатель интерфейса на указанный объект.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
STDMETHODIMP GetMarshalSizeMax(  
   __in REFIID riid,  
   __in_opt void *pv,  
   __in DWORD dwDestContext,  
   __reserved void *pvDestContext,  
   __in DWORD mshlflags,  
   __out DWORD *pSize  
) override;  
```  
  
### <a name="parameters"></a>Параметры  
 *riid*  
 Ссылка на идентификатор интерфейса для маршалинга.  
  
 *PV*  
 Указатель на интерфейс, который должен быть маршалирован; может иметь значение NULL.  
  
 *dwDestContext*  
 Контекст назначения, где должен быть неупакованный указанный интерфейс.  
  
 Укажите одно или несколько значений перечисления MSHCTX.  
  
 В настоящее время распаковка может произойти в другое подразделение текущего процесса (MSHCTX_INPROC) или в другом процессе на том же компьютере, что и текущий процесс (MSHCTX_LOCAL).  
  
 *pvDestContext*  
 Зарезервировано для будущего использования; должен иметь значение NULL.  
  
 *mshlflags*  
 Флаг, указывающий, является ли данных для маршалинга для передачи обратно в клиентском процессе, типичный случай — диска или записываются на глобальной таблицы, где его можно получить несколькими клиентами. Укажите одно или несколько значений перечисления MSHLFLAGS.  
  
 *pSize*  
 После завершения этой операции, указатель на верхнюю границу объема данных, записываемых в поток маршалинга.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если выполнение прошло успешно; в противном случае — значение E_FAIL или E_NOINTERFACE.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** ftm.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс FtmBase](../windows/ftmbase-class.md)