#!/bin/sh

git filter-branch --env-filter '

OLD_EMAIL="utsav@zuzu.ai"

CORRECT_EMAIL="us241098@gmail.com"

if [ "$GIT_COMMITTER_EMAIL" = "utsav@zuzu.ai" ]
then
export GIT_COMMITTER_EMAIL="$CORRECT_EMAIL"
fi
if [ "$GIT_AUTHOR_EMAIL" = "us241077@gmail.com" ]
then
export GIT_AUTHOR_EMAIL="$CORRECT_EMAIL"
fi
' --tag-name-filter cat -- --branches --tags
