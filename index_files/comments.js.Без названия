function commentCreate(num,type) {

  if(localStorage.getItem("commentDate")){
    var commentDate = +localStorage.getItem("commentDate");
  }else{
    var commentDate = new Date().getTime() - 86400000 * 9;
    localStorage.setItem("commentDate", commentDate);
  }

  if (num === 0) {
    subduct = 5120000;
  }else{
    num = num + num * 2;
    subduct = num * 56400 + num * 3 * 2320000;
  }

  var add = commentDate + subduct,
  add = new Date(add),
  monthA = 'Января,Февраля,Марта,Апреля,Мая,Июня,Июля,Августа,Сентября,Октября,Ноября,Декабря'.split(','),
  addDate = add.getDate(),
  addMonth = monthA[add.getMonth()],
  addYear = add.getFullYear(),
  addHours = add.getHours(),
  addMinutes = add.getMinutes();

  if (addHours.toString().length === 1) {
    addHours = Array(2).join('0') + addHours;
  }
  if (addMinutes.toString().length === 1) {
    addMinutes = Array(2).join('0') + addMinutes;
  }

  if (type === 'full') {
    this.textContent = addDate + ' ' + addMonth +' '+ addYear + ' ' + addHours + ':' + addMinutes;
  }else if (type === 'onlyDate') {
    this.textContent = addDate + ' ' + addMonth +' '+ addYear;
  }

}

window.onload = function() {
  var publishedBlock = document.getElementsByClassName("publishedBlock")[0],
  accBlock = document.getElementsByClassName("accBlock")[0],
  commentsBlocks = document.getElementsByClassName("commentsBlocks"),
  lenghtCommentsBlocks = commentsBlocks.length - 1,
  postBlocks = document.getElementsByClassName("postBlocks"),
  lenghtPostBlock = postBlocks.length;

  commentCreate.call(publishedBlock,0,'full');
  commentCreate.call(accBlock,50,'onlyDate');

  for(var i = lenghtCommentsBlocks;i >= 0; i--) {
    commentCreate.call(commentsBlocks[i],i+1,'full');
  }
  for (var i = lenghtPostBlock; i >= 0; i--) {
    commentCreate.call(postBlocks[i],i+15,'onlyDate');
  }
};
