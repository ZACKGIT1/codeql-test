alias nextfeature='
  FILE=".feature_counter";
  if [ ! -f "$FILE" ]; then
    echo 1 > "$FILE";
  else
    VALUE=$(cat "$FILE");
    VALUE=$((VALUE + 1));
    echo $VALUE > "$FILE";
  fi;
  BRANCH="feature$(cat $FILE)";
  git checkout -b "$BRANCH";
  echo "$BRANCH created and checked out."
'
#add this to .bashrc file
