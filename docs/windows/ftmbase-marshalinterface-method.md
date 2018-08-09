---
title: Метод FtmBase::MarshalInterface | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase::MarshalInterface
dev_langs:
- C++
helpviewer_keywords:
- MarshalInterface method
ms.assetid: fc8421b4-06e4-4925-b908-c285fe4790d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 23779cbe0b27680122c6aa3a8f8748c39f28078e
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39647411"
---
# <a name="ftmbasemarshalinterface-method"></a>Метод FtmBase::MarshalInterface
Записывает в поток данные, необходимые для инициализации прокси-объект в какой-либо процесс клиента.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
STDMETHODIMP MarshalInterface(  
   __in IStream *pStm,  
   __in REFIID riid,  
   __in_opt void *pv,  
   __in DWORD dwDestContext,  
   __reserved void *pvDestContext,  
   __in DWORD mshlflags  
) override;  
```  
  
### <a name="parameters"></a>Параметры  
 *pStm*  
 Указатель на поток, который используется во время маршалинга.  
  
 *riid*  
 Ссылка на идентификатор интерфейса для маршалинга. Этот интерфейс должен быть производным от `IUnknown` интерфейс.  
  
 *PV*  
 Указатель на указатель интерфейса, который должен быть маршалирован; может иметь значение NULL, если вызывающий объект не имеет указатель на нужный интерфейс.  
  
 *dwDestContext*  
 Контекст назначения, где должен быть неупакованный указанный интерфейс.  
  
 Укажите одно или несколько значений перечисления MSHCTX.  
  
 Распаковка может произойти в другое подразделение текущего процесса (MSHCTX_INPROC) или в другом процессе на том же компьютере, что и текущий процесс (MSHCTX_LOCAL).  
  
 *pvDestContext*  
 Зарезервировано для будущего использования; должно иметь значение нуль.  
  
 *mshlflags*  
 Указывает, являются ли данные должны быть маршалированы для передачи обратно в клиентском процессе, типичный случай — диска или записываются на глобальной таблицы, где его можно получить несколькими клиентами.  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK  
 Указатель на интерфейс был маршалирован успешно.  
  
 E_NOINTERFACE  
 Указанный интерфейс не поддерживается.  
  
 STG_E_MEDIUMFULL  
 Поток заполнен.  
  
 E_FAIL  
 Операция выполнена со сбоем.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** ftm.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс FtmBase](../windows/ftmbase-class.md)