---
layout: program
title: Symposium Program
---
<table id="program" class="display" style="width:100%"></table>

<script>
    $(document).ready(function() {
        $.ajax({
            url: '{{ "/assets/program.csv" | relative_url }}',
            dataType: 'text',
            success: function(data) {
                var parsedData = Papa.parse(data, { header: true });
                $('#program').DataTable({
                    data: parsedData.data,
                    columns: [
                        { title: "UK Time", data: "UK Time" },
                        { title: "Central European Time", data: "Central European Time" },
                        { title: "Title", data: "Title" },
                        { title: "Speaker", data: "Speaker" },
                        { title: "Affiliation", data: "Affiliation" },
                        { title: "Abstract", data: "Abstract" }
                    ]
                });
            }
        });
    });
</script>
