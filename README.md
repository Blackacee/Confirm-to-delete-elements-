# Confirm-to-delete-elements-
 
<div id="post-102">
 <p>I like Confirm modals.</p>
 <a data-deletepost="post-102">Delete post</a>
</div>
<div id="post-103">
 <p>That's way too cool!</p>
 <a data-deletepost="post-103">Delete post</a>
</div>
// Collect all buttons
var deleteBtn = document.querySelectorAll("[data-deletepost]");
function deleteParentPost(event) {
 event.preventDefault(); // Prevent page scroll jump on anchor click
 if( confirm("Really Delete this post?") ) {
 var post = document.getElementById( this.dataset.deletepost );
 post.parentNode.removeChild(post);
 // TODO: remove that post from database
 } // else, do nothing
}
// Assign click event to buttons
[].forEach.call(deleteBtn, function(btn) {
 btn.addEventListener("click", deleteParentPost, false);
});
