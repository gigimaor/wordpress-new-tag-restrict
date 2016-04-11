# wordpress-new-tag-restrict
Restrict add new tag to post by user role. Only admin can add new tag.
<pre>
function undo_create_term ($term_id, $tt_id, $taxonomy) {
	if (!current_user_can( 'administrator' ))  {
    	if($taxonomy == 'post_tag') {
    		wp_delete_term($term_id,$taxonomy);
   	 	} 	 
    }
}
</pre>
