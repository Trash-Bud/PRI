# Makefile

path = data
FEEDS_FILE := example.txt
FEEDS := "$(shell cat $(FEEDS_FILE) | tr '\n' ' ' | xargs | sed 's/ /\" \"/g')"

export

all: $(FEEDS)
	$(MAKE) $(HASHES)


$(FEEDS): $(path)
	$(eval HASH := $(shell echo -n $@ | md5sum | sed 's/ //g' | sed 's/-//g'))
	$(eval HASHES += $(HASH))
	curl -s -Lo $(path)/$(HASH).html "http://$@"


# Rule to parse each feed
$(HASHES): % :$(path)/%.html
	cat $< | grep -Eo '(http|https)://[a-zA-Z0-9./?=_-]+' | grep -E '\.pt/.+' | sort | uniq | tr ' ' "\n" > $(path)/$@.txt
	cat $(path)/$@.txt | tr \\n \\0 | xargs -0 -n1 -I % curl % -O %.html
	
$(path):
	mkdir $@
	echo "Created folder $@"

clean:
	rm  -Rf $(path)
	echo "Cleaning"
