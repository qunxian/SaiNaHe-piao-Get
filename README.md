// ==UserScript==
// @name          SaiNaHe piao Get
// @namespace     https://github.com/saintwinkle/SNH48-Get-Ticket
// @version       0.0.1
// @author        qunxian
// @description   48商城票务脚本
// @match         http://shop.48.cn/tickets/item/63?seat_type=*
// @match         http://shop.48.cn/TOrder/Item/160413-2-10014*
// @match         http://admin.48.cn/tickets/item/63?seat_type=3
// @match         http://shop.48.cn/TOrder/Item/160413-2-10014*
// @run-at        document-end
// ==/UserScript==

var number = 1;

var ticket = {
  quick: 1,
  spec: [],
  ticket_id: tickets_id,
  captcha: '0',
  is_donation: $('#is_donation').val(),
  number: number,
  donation_number: $('#donation_number').val(),
  parent: 0
}

var fn = function() {
  $.post('/test.php', {
    tickets_id: tickets_id,
    tickets: JSON.stringify(goods),
    step: 'default'
  }, function() {
    location.href = '/checkout.php?step=checkout';
  });
};

fn();
setTimeout(fn, 100);
