

/*
  查询待发货数量,  pay_time 是支付尾款时间 ,order_time ,是订单时间.
  商品数量
*/

SELECT
td.goods_barcode,
t.store_id_erp,
td.goods_name,
SUM(td.pay_amount),
SUM(td.goods_num)  as goods_num

FROM trade_detail  AS td
LEFT JOIN trade as t  on  t.id_onl = td.trade_id_onl
WHERE t.order_time >= '2019-04-12 00:00:00'
AND t.order_time <= '2019-04-12 23:59:59'
AND t.status_label_onl = '待发货'
AND td.goods_barcode IN ("692651987160","MB001-100")
GROUP BY td.goods_barcode,t.store_id_erp
ORDER BY goods_num DESC
